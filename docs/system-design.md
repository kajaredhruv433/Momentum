# Momentum Engineering Principles

Momentum combines an adaptive interview with bounded session control and optional technical assessment tools. This page summarizes the public engineering principles behind that product behavior.

## Adaptive questions, controlled lifecycle

The panel can respond to candidate answers and choose follow-ups, new competency areas, or available tools. A platform-controlled Normal, Extended, and Final stage lifecycle provides a defined session boundary. Adaptivity governs what is asked; the controller governs when the interview moves between stages and ends.

## Multiple forms of evidence

Different skills require different response modes. Momentum supports live verbal answers, a system-design canvas, short typed code or SQL responses, and a focused repository coding round. The evaluator can consider the evidence available in the session instead of relying on one answer format.

## Background preparation

Repository analysis and challenge preparation happen while the interview continues. Keeping that work outside the live turn path lets the conversation proceed and allows the coding round to become available when preparation is complete.

## Isolated assessment

Repository challenges use a temporary isolated workspace based on the selected project. Candidate edits remain in that workspace and are not pushed to GitHub. Focused test execution is offered when the target behavior can be tested practically without recreating unrelated project infrastructure.

## Correctness before approach

The evaluator first checks whether the submitted code restores the intended behavior. Only a correct result is compared with the reference implementation's approach. This keeps correctness and solution quality as separate evaluation questions.

## Human-readable guidance

The assessment problem describes the affected behavior and where the candidate should investigate. The contextual assistant can explain code and concepts while withholding the completed fix. Focused tests are locked from candidate file operations, preserving the distinction between understanding the problem and inspecting the validation oracle.

## Public architecture boundary

The architecture docs describe product responsibilities and data flow. They intentionally omit source-level orchestration, proprietary challenge-generation prompts, provider credentials, deployment configuration, and internal evaluation algorithms.
