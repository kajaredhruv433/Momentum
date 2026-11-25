# Momentum Engineering Principles

Momentum combines an adaptive interview with bounded session control and optional technical assessment tools. This page summarizes the public engineering principles behind that product behavior.

## Frontend and backend design

Momentum is implemented as a full-stack web application with separate user-facing surfaces and a shared backend:

| Surface or service | Stack | Main responsibility |
|---|---|---|
| Candidate/recruiter portal | Next.js, React, TypeScript | Hiring workflows, job and application experiences, and interview setup. |
| Live interview room | React, Vite | Realtime interview controls, transcript, canvas, typing pad, and repository challenge editor. |
| Backend services | Python, FastAPI, Uvicorn | Product APIs, interview lifecycle, data access, realtime events, and third-party integrations. |
| Data and execution | MongoDB, SQLite, Daytona | Product and interview persistence, assessment lifecycle data, and isolated code workspaces. |

The portal and the live interview room have different interaction patterns, but both use backend-owned application state. That lets the platform combine a conventional recruitment product with an interactive realtime session without making the browser responsible for authoritative interview progression or assessment outcomes.

## Backend and frontend engineering

- **Frontend composition:** The portal and interview room are separate React applications tailored to distinct product journeys. The interview UI presents role turns, candidate responses, transcript, drawing canvas, typing pad, and assessment editor as connected states.
- **API and realtime boundaries:** Conventional product actions use backend APIs; live interview progress and speech use realtime communication. Both feed into server-managed interview state.
- **Workflow orchestration:** The backend coordinates interview stages, next-turn decisions, readiness for a repository challenge, assessment submission, and resumption of the interview.
- **Persistence and lifecycle:** Product/interview data and assessment lifecycle state have explicit storage responsibilities, allowing an interview session and a temporary coding assessment to progress independently.
- **External service integration:** GitHub, speech services, model endpoints, and Daytona are integrated as supporting capabilities behind backend workflows.
- **Temporary execution boundary:** Repository changes and optional tests execute in isolated temporary workspaces; the source repository remains unchanged.

These boundaries matter because realtime UI state, external provider availability, persistent interview state, and candidate-controlled code all have different failure and trust characteristics.

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
