# AGENTS.md — Resume Project Execution Contract

This file is the first operational source of truth after dialogue compression or context restoration.

## Project purpose

- Build truthful, evidence-based resumes and supporting job-search documents for Dmitry Mikhailovich Panevin.
- Preserve the complete employment history while producing separate targeted resume variants where necessary.
- Never discard experience before evaluating its relevance to target roles.
- Do not present hypotheses, training, experiments, or self-study as paid employment or production experience.

## User environment

- Shell: Git Bash MINGW64 on Windows.
- Canonical local repository path: `~/projects/resume-project`.
- Canonical GitHub repository: `https://github.com/dmitya30/resume-project`.
- The assistant writes commands and patches; the user applies them.
- Every executable patch must begin with `cd ~/projects/resume-project`.
- Never use `exit`, `exit 1`, `set -e`, or commands that close the active Git Bash session.

## Context restoration order

After dialogue compression or context loss, read sources in this order:

1. `AGENTS.md`.
2. `docs/resume-methodology.md`.
3. `docs/CONTEXT.md`.
4. `docs/CANDIDATE_STATE.md`.
5. `docs/PROJECT_INVENTORY.md`.
6. `docs/archive/FULL_PROTOCOL_2026-08-27.md` only for historical recovery, provenance checks, and unresolved details.
7. Verify the current Git HEAD and working-tree state before proposing repository changes.

Do not reconstruct missing facts from memory when the repository can be inspected. If an uncommitted local file is unavailable, ask the user to provide it instead of guessing its content.

## Context and network economy

- Treat the active dialogue memory as the primary working context while it remains intact.
- Minimize repeated repository reads and web searches: use them only when they are necessary for correctness, required by the methodology, needed to inspect a file before changing it, or explicitly requested by the user.
- Do not re-read unchanged repository files merely to reconfirm facts already retained in the active context.
- Do not repeat market searches whose results are already sufficient for the current decision.
- After dialogue compression, context loss, a suspected contradiction, or uncertainty about a source-controlled fact, restore context from the repository in the prescribed order instead of guessing.
- Current market facts, live vacancies, platform behavior, and named external entities must still be verified when the task materially depends on their present state.
- Prefer one focused retrieval pass over multiple overlapping calls, and retain the resulting conclusions in the working context and repository documents.

## Source hierarchy and evidence

- User corrections and explicit confirmations override earlier dialogue summaries.
- Employment documents and official extracts are primary evidence for dates, employers, and official job titles.
- Official job titles must remain unchanged. Functional specialization may be explained separately through actual duties and achievements.
- Public sources may verify organizations, websites, and public registrations, but do not prove personal authorship or responsibility without user confirmation.
- A personal contextual profile is a source of hypotheses, not automatic proof.
- Never invent dates, metrics, technologies, responsibilities, clients, revenue, project status, or results.
- If handwriting or a source is unreadable, mark it as unresolved and ask for clarification.

Use these evidence markers in internal working documents:

- `[Д]` — confirmed by a document or official extract.
- `[П]` — explicitly confirmed by the applicant.
- `[В]` — checked in a public web source.
- `[Г]` — hypothesis requiring confirmation.
- `[Р]` — relevant to a selected target role.
- `[N]` — background or currently non-target experience.

## Resume methodology rules

- Follow `docs/resume-methodology.md` and work through its phases rather than jumping directly to final wording.
- Separate official employment, entrepreneurship, self-employment, freelance work, personal projects, training, and self-study.
- Describe achievements conservatively and prefer verifiable scope, actions, and outcomes.
- Do not modernize historical experience by assigning technologies or role names that were not used at the time.
- Do not hide career gaps by inventing project work.
- Personal bankruptcy is not included in a resume unless a specific legal or application context requires disclosure.
- Self-employment is currently an internal fact and is not a blocker for employment. Include it only when relevant to a selected resume strategy.
- Prepare multiple targeted resumes when one document would mix incompatible positioning.

## Current strategic direction

- Primary direction to validate: AI and business-process automation, n8n integrations, Telegram bots, and related technical implementation.
- Secondary direction for faster employment: system administrator, IT engineer, infrastructure specialist, or technical support specialist.
- The final priority depends on verification of recent projects and market fit.
- Earlier unsuccessful positioning as an AI automation engineer is diagnostic information, not a reason to discard the direction.

## Document maintenance

- Keep current facts in compact structured documents and replace outdated or incomplete statements instead of endlessly appending corrections.
- Preserve the full historical protocol as a recovery and provenance source, not as the primary everyday context.
- Record unresolved contradictions explicitly.
- Keep detailed project evidence separate from resume-ready wording.
- Owner-facing conclusions and drafts are written in Russian.
- Internal technical registers may be written in English.
- Do not hard-wrap owner-facing prose at a fixed column width.
- Every tracked text file should normally end with exactly one newline.
- Empty lines inside documents are valid and are never blockers.
- Additional blank lines at EOF are warnings, not blockers by themselves.
- Spaces or tabs at the ends of lines are formatting defects and should be removed.

## Repository patch rules

- Deliver each operational change as one complete executable code block.
- Do not use heredoc syntax.
- Do not pass large scripts through `python -c`, `bash -c`, or another single command-line argument; Windows Git Bash may fail with `Argument list too long`.
- For large generated patches, write the program to a temporary file under `.git/`, execute it, and remove it afterward.
- Do not split one operation across multiple copied command blocks.
- Do not invent repository paths, schemas, or filenames before inspecting the repository.
- Prefer deterministic full-file replacements for small control documents and narrowly scoped edits for source records.
- Do not ask the user to repair assistant-generated code manually.
- If a delivered script has one localized defect, provide a minimal corrective patch rather than repeating unrelated operations.
- Do not print full Git diffs from executable scripts.
- Before commit, verify the exact staged file list and run `git diff --cached --check`.
- A commit-and-push operation may be included only when explicitly requested or approved by the user.
- On success, report only concise validation, commit, push, and status information. Diagnostic output is allowed on failure.

## Privacy and safety

- Do not commit passport data, SNILS, signatures, QR codes, bank details, private addresses, credentials, tokens, private contracts, or unredacted confidential records.
- Public identifiers are included only when necessary and explicitly approved.
- Before proposing publication of evidence, separate public portfolio material from private supporting records.

## Current recovery checkpoint

- Repository context was initialized at commit `f7cf603`.
- `docs/CONTEXT.md` is the compact operational recovery point.
- `docs/CANDIDATE_STATE.md` is the current replaceable source of accepted candidate facts, risks, unresolved questions, and resume-safe wording.
- `docs/archive/FULL_PROTOCOL_2026-08-27.md` remains the immutable historical recovery and provenance source.
- The accepted ООО «Артэкс» corrections are reflected in `docs/CANDIDATE_STATE.md`.
- The modern-project inventory is stored in `docs/PROJECT_INVENTORY.md`; a limited public evidence review was completed on 02.09.2026. Initial job-market research was completed on 03.09.2026 and recorded in `docs/MARKET_RESEARCH.md` and `docs/REQUIREMENTS_MATRIX.md`. The old HH resume audit is recorded in `docs/HH_PROFILE_AUDIT.md`. The current phase is building and launching two new HH resumes: «Инженер по автоматизации и AI-интеграциям» and «IT-инженер / системный администратор». Only HH is used at this stage; Habr Career and other channels are deferred.
- The field-by-field HH wizard map, current main-resume settings, skill levels, work-experience blocks and remaining launch checks are stored in `docs/HH_WIZARD_GUIDE.md`.
- Do not delete or rewrite the historical protocol without explicit user approval.

## Public text character policy

- In public-facing texts, including resumes, cover letters, profile descriptions, vacancy responses, portfolio captions, and messages to employers, use plain keyboard-safe punctuation.
- Cyrillic letters are allowed. The only allowed typographic punctuation exception is Russian guillemets: `«»`.
- Do not use Unicode em dashes or en dashes. Use the ASCII hyphen-minus: `-`.
- Do not use Unicode bullets, arrows, non-breaking spaces, curly quotes, emoji, or decorative symbols. Use `-`, `->`, ordinary spaces, and `«»` instead.
- Before delivering public text, check and normalize its punctuation according to this rule.
