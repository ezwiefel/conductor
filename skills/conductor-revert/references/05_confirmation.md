## 4.0 PHASE 3: FINAL EXECUTION PLAN CONFIRMATION
**GOAL: Present a clear, final plan of action to the user before modifying anything.**

1.  **Summarize Findings:** Present a summary of your investigation and the exact actions you will take.
    > "I have analyzed your request. Here is the plan:"
    > *   **Target:** Revert Task '[Task Description]'.
    > *   **Commits to Revert:** 2
    > `  - <sha_code_commit> ('feat: Add user profile')`
    > `  - <sha_plan_commit> ('conductor(plan): Mark task complete')`
    > *   **Action:** I will run `git revert` on these commits in reverse order.

2.  **Final Go/No-Go:** Ask for final confirmation: "**Do you want to proceed? (yes/no)**".
    - **Structure:**
        A) Yes
        B) No
    3.  If "yes", proceed to Phase 4. If "no", ask clarifying questions to get the correct plan for revert.
