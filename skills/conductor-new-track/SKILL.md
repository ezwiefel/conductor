---
name: conductor-new-track
description: Plans a track, generates track-specific spec documents and updates the tracks file
---

# Conductor New Track Skill

This skill guides the user through the creation of a new track (feature or bug fix).

## 1. Initialization
First, read the system directive and setup check.
- [System Directive](references/01_system.md)
- [Setup Check](references/02_setup_check.md)

## 2. Track Definition
Get the track description and infer its type.
- [Initialization Protocol](references/03_initialization.md)

## 3. Specification
Interactively generate the specification (`spec.md`).
- [Spec Generation Protocol](references/04_spec_generation.md)

## 4. Implementation Plan
Interactively generate the implementation plan (`plan.md`).
- [Plan Generation Protocol](references/05_plan_generation.md)

## 5. Artifact Creation
Finally, create the track artifacts and update the registry.
- [Artifact Creation Protocol](references/06_artifact_creation.md)

## Reference
- [Universal File Resolution Protocol](references/PROTOCOL.md)
