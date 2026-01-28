## 5.0 TRACK CLEANUP
**PROTOCOL: Offer to archive or delete the completed track.**

1.  **Execution Trigger:** This protocol MUST only be executed after the current track has been successfully implemented and the `SYNCHRONIZE PROJECT DOCUMENTATION` step is complete.

2.  **Ask for User Choice:** You MUST prompt the user with the available options for the completed track.
    > "Track '<track_description>' is now complete. What would you like to do?
    > A.  **Archive:** Move the track's folder to `conductor/archive/` and remove it from the tracks file.
    > B.  **Delete:** Permanently delete the track's folder and remove it from the tracks file.
    > C.  **Skip:** Do nothing and leave it in the tracks file.
    > Please enter the number of your choice (A, B, or C)."

3.  **Handle User Response:**
    *   **If user chooses "A" (Archive):**
        i.   **Create Archive Directory:** Check for the existence of `conductor/archive/`. If it does not exist, create it.
        ii.  **Archive Track Folder:** Move the track's folder from its current location (resolved via the **Tracks Directory**) to `conductor/archive/<track_id>`.
        iii. **Remove from Tracks File:** Read the content of the **Tracks Registry** file, remove the entire section for the completed track (the part that starts with `---` and contains the track description), and write the modified content back to the file.
        iv.  **Commit Changes:** Stage the **Tracks Registry** file and `conductor/archive/`. Commit with the message `chore(conductor): Archive track '<track_description>'`.
        v.   **Announce Success:** Announce: "Track '<track_description>' has been successfully archived."
    *   **If user chooses "B" (Delete):**
        i. **CRITICAL WARNING:** Before proceeding, you MUST ask for a final confirmation due to the irreversible nature of the action.
            > "WARNING: This will permanently delete the track folder and all its contents. This action cannot be undone. Are you sure you want to proceed? (yes/no)"
        ii. **Handle Confirmation:**
            - **If 'yes'**:
                a. **Delete Track Folder:** Resolve the **Tracks Directory** and permanently delete the track's folder from `<Tracks Directory>/<track_id>`.
                b. **Remove from Tracks File:** Read the content of the **Tracks Registry** file, remove the entire section for the completed track, and write the modified content back to the file.
                c. **Commit Changes:** Stage the **Tracks Registry** file and the deletion of the track directory. Commit with the message `chore(conductor): Delete track '<track_description>'`.
                d. **Announce Success:** Announce: "Track '<track_description>' has been permanently deleted."
            - **If 'no' (or anything else)**:
                a. **Announce Cancellation:** Announce: "Deletion cancelled. The track has not been changed."
    *   **If user chooses "C" (Skip) or provides any other input:**
        *   Announce: "Okay, the completed track will remain in your tracks file for now."
