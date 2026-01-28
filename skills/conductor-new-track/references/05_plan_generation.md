### 2.3 Interactive Plan Generation (`plan.md`)

1.  **State Your Goal:** Once `spec.md` is approved, announce:
    > "Now I will create an implementation plan (plan.md) based on the specification."

2.  **Generate Plan:**
    *   Read the confirmed `spec.md` content for this track.
    *   Resolve and read the **Workflow** file (via the **Universal File Resolution Protocol** using the project's index file).
    *   Generate a `plan.md` with a hierarchical list of Phases, Tasks, and Sub-tasks.
    *   **CRITICAL:** The plan structure MUST adhere to the methodology in the **Workflow** file (e.g., TDD tasks for "Write Tests" and "Implement").
    *   Include status markers `[ ]` for **EVERY** task and sub-task. The format must be:
        - Parent Task: `- [ ] Task: ...`
        - Sub-task: `    - [ ] ...`
    *   **CRITICAL: Inject Phase Completion Tasks.** Determine if a "Phase Completion Verification and Checkpointing Protocol" is defined in the **Workflow**. If this protocol exists, then for each **Phase** that you generate in `plan.md`, you MUST append a final meta-task to that phase. The format for this meta-task is: `- [ ] Task: Conductor - User Manual Verification '<Phase Name>' (Protocol in workflow.md)`.

3.  **User Confirmation:** Present the drafted `plan.md` to the user for review and approval.
    > "I've drafted the implementation plan. Please review the following:"
    >
    > ```markdown
    > [Drafted plan.md content here]
    > ```
    >
    > "Does this plan look correct and cover all the necessary steps based on the spec and our workflow? Please suggest any changes or confirm."
    Await user feedback and revise the `plan.md` content until confirmed.
