# Momentum Release History

This page summarizes the public-facing evolution of Momentum. It describes product behavior and architecture at a high level; it intentionally does not include production source code, prompts, credentials, or internal implementation details.

## Version 2.1 — Foundation

- Established the recruitment portal and adaptive, multi-role interview experience.
- Introduced recruiter job and candidate workflows, interview transcripts, and evaluation reports.
- Used Agora for interview audio transport and a multi-provider reasoning setup.

## Version 2.2 — Direct Voice Pipeline

- Replaced the Agora audio path with browser audio capture and a backend relay for direct speech services.
- Added real-time transcription, synthesized interviewer speech, and interruption support.
- Expanded adaptive turn decisions, panel selection, and optional system-design drawing analysis.
- Added a server-controlled interview clock and more structured evidence-based reports.

## Version 2.3 — Interview Experience Refinement

- Refined the interview prompts and response handling so generated questions better followed the intended interview flow.
- Continued the adaptive multi-persona interview, voice interaction, and system-design canvas experience.
- Improved the candidate experience around speech interruption and transitions between interviewer turns.
- Kept the recruitment portal and interview room as connected parts of the same product.

## Version 3.0 and 3.2 — Unified Platform and Interviewer Improvements

Versions 3.0 and 3.2 are presented together here because 3.2 is an incremental refinement of the same product direction.

- Consolidated recruitment and interview APIs behind a unified backend application, with the interview room served as part of the product.
- Refined the interview lifecycle, stage handling, interviewer responses, and candidate context flow.
- Added resume-aware analysis and coding-interview support alongside the voice interview experience.
- Simplified the interview reasoning integration around a shared model interface, while retaining explicit controller ownership of state, timing, and report access.
- Improved job discovery and persistence around the existing recruitment workflows.
- Preserved recruiter-only access to evaluation reports and candidate-facing completion status.

## Public Showcase Scope

This repository documents the evolution through diagrams, workflows, API descriptions, and synthetic examples. It does not distribute production implementations. Any code examples in this repository should remain generic, non-secret, and safe to publish; the private snapshots are reference material only.
