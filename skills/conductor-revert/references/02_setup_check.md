## 1.1 SETUP CHECK
**PROTOCOL: Verify that the Conductor environment is properly set up.**

1.  **Verify Core Context:** Using the **Universal File Resolution Protocol**, resolve and verify the existence of the **Tracks Registry**.

2.  **Verify Track Exists:** Check if the **Tracks Registry** is not empty.

3.  **Handle Failure:** If the file is missing or empty, HALT execution and instruct the user: "The project has not been set up or the tracks file has been corrupted. Please run `/conductor:setup` to set up the plan, or restore the tracks file."
