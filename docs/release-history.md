# Momentum Release History

This history presents Momentum as three product releases. Earlier implementation milestones are grouped into the Version 1 and Version 2 product story rather than split into minor-version labels.

| Release | Focus | Capabilities introduced |
|---|---|---|
| **Version 1 — Interview foundation** | Establish the recruitment and interview product. | Candidate and recruiter workflows, resume-aware interview context, multi-role interviewer experience, interview transcripts, and post-interview evaluation. |
| **Version 2 — Adaptive voice interview** | Make the interview conversational, multimodal, and bounded. | Realtime voice interaction and transcription, coordinated interviewer turns, adaptive follow-ups, a system-design canvas with visual analysis, and a controlled Normal → Extended → Final lifecycle. |
| **Version 3 — Project-grounded assessment** | Add direct evidence from the candidate's own project work. | GitHub connection and repository selection, background project analysis, an in-interview typing pad, an isolated repository-specific bug-fix round, conditional focused test execution, guidance-only AI assistance, and correctness-first solution evaluation. |

## Version 1 — Interview foundation

Momentum began as a recruitment and interview platform: candidates and recruiters could move through the hiring workflow, and an AI-led panel could use role and resume context to conduct an interview. The product produced a structured post-interview assessment from the session.

## Version 2 — Adaptive voice interview

Version 2 developed the interview into a live, adaptive experience. Interviewer roles coordinate through a shared controller, take turns, and use candidate answers to select follow-up questions and competency areas. Voice interaction and transcription support a natural conversation, while the optional system-design canvas adds a visual response mode.

The interview uses three bounded stages—Normal, Extended, and Final. The stage lifecycle and timer are controlled by the platform; the question path remains adaptive within those bounds. This balances flexible probing with a predictable session length.

## Version 3 — Project-grounded assessment

Version 3 keeps the Version 2 interview and adds two ways to test practical knowledge:

- **Typing pad:** When an interviewer asks for a short syntax, coding, or SQL response, the pad appears in the interview room and accepts a typed answer.
- **Repository assessment:** A candidate may connect GitHub and select a project they discussed. The panel asks about their role and contribution while analysis prepares a focused challenge in the background. When ready, a temporary isolated workspace presents a bug-fix problem based on a relevant code area.

The assessment adapts to what can be executed safely and meaningfully. A focused Run action and hidden, locked test are provided when the selected code can be tested in a practical isolated setup. When it depends on heavyweight training, services, or other infrastructure that is not appropriate to reproduce, the challenge can be evaluated without installing those dependencies or offering a Run action.

The candidate can use an assistant for contextual explanations and concepts, with a restriction against supplying the completed fix. Evaluation is hierarchical: correctness is checked first against the original project behavior; only a correct submission is compared with the reference approach. Candidate edits remain in the temporary assessment workspace and are not pushed to GitHub.

## Public showcase scope

This repository documents product behavior and high-level architecture. It does not distribute private production implementations, model prompts, credentials, or proprietary challenge-generation logic.
