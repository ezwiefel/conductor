## 2.0 PHASE 1: INTERACTIVE TARGET SELECTION & CONFIRMATION
**GOAL: Guide the user to clearly identify and confirm the logical unit of work they want to revert before any analysis begins.**

1.  **Initiate Revert Process:** Your first action is to determine the user's target.

2.  **Check for a User-Provided Target:** First, check if the user provided a specific target as an argument (e.g., `/conductor:revert track <track_id>`).
    *   **IF a target is provided:** Proceed directly to the **Direct Confirmation Path (A)** below.
    *   **IF NO target is provided:** You MUST proceed to the **Guided Selection Menu Path (B)**. This is the default behavior.

3.  **Interaction Paths:**

    *   **PATH A: Direct Confirmation**
        1.  Find the specific track, phase, or task the user referenced in the **Tracks Registry** or **Implementation Plan** files (resolved via **Universal File Resolution Protocol**).
        2.  Ask the user for confirmation: "You asked to revert the [Track/Phase/Task]: '[Description]'. Is this correct?".
            - **Structure:**
                A) Yes
                B) No
        3.  If "yes", establish this as the `target_intent` and proceed to Phase 2. If "no", ask clarifying questions to find the correct item to revert.

    *   **PATH B: Guided Selection Menu**
        1.  **Identify Revert Candidates:** Your primary goal is to find relevant items for the user to revert.
            *   **Scan All Plans:** You MUST read the **Tracks Registry** and every track's **Implementation Plan** (resolved via **Universal File Resolution Protocol** using the track's index file).
            *   **Prioritize In-Progress:** First, find **all** Tracks, Phases, and Tasks marked as "in-progress" (`[~]`).
            *   **Fallback to Completed:** If and only if NO in-progress items are found, find the **5 most recently completed** Tasks and Phases (`[x]`).
        2.  **Present a Unified Hierarchical Menu:** You MUST present the results to the user in a clear, numbered, hierarchical list grouped by Track. The introductory text MUST change based on the context.
            *   **Example when in-progress items are found:**
                > "I found multiple in-progress items. Please choose which one to revert:
                >
                > Track: track_20251208_user_profile
                >   1) [Phase] Implement Backend API
                >   2) [Task] Update user model
                >
                > 3) A different Track, Task, or Phase."
            *   **Example when showing recently completed items:**
                > "No items are in progress. Please choose a recently completed item to revert:
                >
                > Track: track_20251208_user_profile
                >   1) [Phase] Foundational Setup
                >   2) [Task] Initialize React application
                >
                > Track: track_20251208_auth_ui
                >   3) [Task] Create login form
                >
                > 4) A different Track, Task, or Phase."
        3.  **Process User's Choice:**
            *   If the user's response is **A** or **B**, set this as the `target_intent` and proceed directly to Phase 2.
            *   If the user's response is **C** or another value that does not match A or B, you must engage in a dialogue to find the correct target. Ask clarifying questions like:
                * "What is the name or ID of the track you are looking for?"
                * "Can you describe the task you want to revert?"
                * Once a target is identified, loop back to Path A for final confirmation.

4.  **Halt on Failure:** If no completed items are found to present as options, announce this and halt.
