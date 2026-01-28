### 2.2 Interactive Specification Generation (`spec.md`)

1.  **State Your Goal:** Announce:
    > "I'll now guide you through a series of questions to build a comprehensive specification (`spec.md`) for this track."

2.  **Questioning Phase:** Ask a series of questions to gather details for the `spec.md`. Tailor questions based on the track type (Feature or Other).
    *   **CRITICAL:** You MUST ask these questions sequentially (one by one). Do not ask multiple questions in a single turn. Wait for the user's response after each question.
    *   **General Guidelines:**
        *   Refer to information in **Product Definition**, **Tech Stack**, etc., to ask context-aware questions.
        *   Provide a brief explanation and clear examples for each question.
        *   **Strongly Recommendation:** Whenever possible, present 2-3 plausible options (A, B, C) for the user to choose from.
        *   **Mandatory:** The last option for every multiple-choice question MUST be "Type your own answer".

        *   **1. Classify Question Type:** Before formulating any question, you MUST first classify its purpose as either "Additive" or "Exclusive Choice".
            *   Use **Additive** for brainstorming and defining scope (e.g., users, goals, features, project guidelines). These questions allow for multiple answers.
            *   Use **Exclusive Choice** for foundational, singular commitments (e.g., selecting a primary technology, a specific workflow rule). These questions require a single answer.

        *   **2. Formulate the Question:** Based on the classification, you MUST adhere to the following:
            *   **Strongly Recommended:** Whenever possible, present 2-3 plausible options (A, B, C) for the user to choose from.
            *   **If Additive:** Formulate an open-ended question that encourages multiple points. You MUST then present a list of options and add the exact phrase "(Select all that apply)" directly after the question.
            *   **If Exclusive Choice:** Formulate a direct question that guides the user to a single, clear decision. You MUST NOT add "(Select all that apply)".

        *   **3. Interaction Flow:**
            *   **CRITICAL:** You MUST ask questions sequentially (one by one). Do not ask multiple questions in a single turn. Wait for the user's response after each question.
            *   The last option for every multiple-choice question MUST be "Type your own answer".
            *   Confirm your understanding by summarizing before moving on to the next question or section..

    *   **If FEATURE:**
        *   **Ask 3-5 relevant questions** to clarify the feature request.
        *   Examples include clarifying questions about the feature, how it should be implemented, interactions, inputs/outputs, etc.
        *   Tailor the questions to the specific feature request (e.g., if the user didn't specify the UI, ask about it; if they didn't specify the logic, ask about it).

    *   **If SOMETHING ELSE (Bug, Chore, etc.):**
        *   **Ask 2-3 relevant questions** to obtain necessary details.
        *   Examples include reproduction steps for bugs, specific scope for chores, or success criteria.
        *   Tailor the questions to the specific request.

3.  **Draft `spec.md`:** Once sufficient information is gathered, draft the content for the track's `spec.md` file, including sections like Overview, Functional Requirements, Non-Functional Requirements (if any), Acceptance Criteria, and Out of Scope.

4.  **User Confirmation:** Present the drafted `spec.md` content to the user for review and approval.
    > "I've drafted the specification for this track. Please review the following:"
    >
    > ```markdown
    > [Drafted spec.md content here]
    > ```
    >
    > "Does this accurately capture the requirements? Please suggest any changes or confirm."
    Await user feedback and revise the `spec.md` content until confirmed.
