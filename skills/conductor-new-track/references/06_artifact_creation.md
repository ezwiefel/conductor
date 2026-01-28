### 2.4 Create Track Artifacts and Update Main Plan

1.  **Check for existing track name:** Before generating a new Track ID, resolve the **Tracks Directory** using the **Universal File Resolution Protocol**. List all existing track directories in that resolved path. Extract the short names from these track IDs (e.g., ``shortname_YYYYMMDD`` -> `shortname`). If the proposed short name for the new track (derived from the initial description) matches an existing short name, halt the `newTrack` creation. Explain that a track with that name already exists and suggest choosing a different name or resuming the existing track.
2.  **Generate Track ID:** Create a unique Track ID (e.g., ``shortname_YYYYMMDD``).
3.  **Create Directory:** Create a new directory for the tracks: `<Tracks Directory>/<track_id>/`.
4.  **Create `metadata.json`:** Create a metadata file at `<Tracks Directory>/<track_id>/metadata.json` with content like:
    ```json
    {
      "track_id": "<track_id>",
      "type": "feature", // or "bug", "chore", etc.
      "status": "new", // or in_progress, completed, cancelled
      "created_at": "YYYY-MM-DDTHH:MM:SSZ",
      "updated_at": "YYYY-MM-DDTHH:MM:SSZ",
      "description": "<Initial user description>"
    }
    ```
    *   Populate fields with actual values. Use the current timestamp.
5.  **Write Files:**
    *   Write the confirmed specification content to `<Tracks Directory>/<track_id>/spec.md`.
    *   Write the confirmed plan content to `<Tracks Directory>/<track_id>/plan.md`.
    *   Write the index file to `<Tracks Directory>/<track_id>/index.md` with content:
        ```markdown
        # Track <track_id> Context

        - [Specification](./spec.md)
        - [Implementation Plan](./plan.md)
        - [Metadata](./metadata.json)
        ```
6.  **Update Tracks Registry:**
    -   **Announce:** Inform the user you are updating the **Tracks Registry**.
    -   **Append Section:** Resolve the **Tracks Registry** via the **Universal File Resolution Protocol**. Append a new section for the track to the end of this file. The format MUST be:
        ```markdown

        ---

        - [ ] **Track: <Track Description>**
        *Link: [./<Relative Track Path>/](./<Relative Track Path>/)*
        ```
        (Replace `<Relative Track Path>` with the path to the track directory relative to the **Tracks Registry** file location.)
7.  **Announce Completion:** Inform the user:
    > "New track '<track_id>' has been created and added to the tracks file. You can now start implementation by running `/conductor:implement`."
