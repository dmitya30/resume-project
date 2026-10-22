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

- The active dialogue is the project-level orchestrator and maintains the overall candidate, resume, and job-search strategy.
- Maintain three separate, completed, and truthful resume directions:
  - AI and business-process automation, n8n integrations, API, Telegram bots, LLM, and self-hosted systems;
  - IT engineering, system administration, infrastructure, and technical support;
  - 1C administration and support based only on confirmed platform maintenance, user support, CryptoPro CSP, qualified electronic signature, EDI, and adjacent infrastructure experience.
- Do not position the candidate as a 1C developer or an experienced 1C consultant without separately confirmed practical experience.
- The active vacancy-discovery sources are HH, Hirify, TalentMove, Remote-job, relevant Telegram channels, and direct employer career sites.
- Do not submit applications through HH. Use it for vacancy discovery, resume publication, maintenance, links, and export.
- Treat aggregators primarily as discovery sources. Look for the original publication, employer site, career page, public email, recruiter, hiring manager, or another direct route.
- Prefer written direct contact, especially email. A selective phone call is allowed when no suitable written route exists.
- Paid-response services and paid access to contacts on YouDo, Profi, and similar platforms are excluded.
- Search for permanent, remote, hybrid, part-time, project, and fractional work.
- Develop a parallel client and partner channel for external IT support, infrastructure, Linux/VPS, integrations, automation, CryptoPro CSP, qualified electronic signatures, and related confirmed services.
- Record manual-search observations in `docs/JOB_SEARCH_LOG.md`.
- Treat career-channel recommendations as external hypotheses, not verified market facts. Their provenance and project decisions are recorded in `docs/CAREER_CHANNEL_FINDINGS.md`.
- Vacancy-search automation remains in the backlog until manual evidence justifies a new specification.
- Do not modify files under `job-search/` or `job-search/workflows/` from the orchestrator dialogue unless the user explicitly starts a subsystem task and the exact current files are inspected.

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
- A requested repository change is approval to complete the full cycle immediately: validate, stage, commit, and push in the same executable operation. Stop before commit or push only when the user explicitly requests review without committing, validation finds a critical defect, or push fails.
- On success, report only concise validation, commit, push, and status information. Diagnostic output is allowed on failure.

## Privacy and safety

- Do not commit passport data, SNILS, signatures, QR codes, bank details, private addresses, credentials, tokens, private contracts, or unredacted confidential records.
- Public identifiers are included only when necessary and explicitly approved.
- Before proposing publication of evidence, separate public portfolio material from private supporting records.

## Current recovery checkpoint

- `docs/CONTEXT.md` is the compact operational recovery point for the overall project.
- `docs/CANDIDATE_STATE.md` is the source of accepted candidate facts, risks, unresolved questions, and resume-safe wording.
- `docs/JOB_SEARCH_STRATEGY.md` is the current source for channels, priorities, direct-contact policy, experiments, and the automation backlog.
- `docs/JOB_SEARCH_LOG.md` is the append-only operational journal for manually processed vacancies and direct contacts.
- `docs/CAREER_CHANNEL_FINDINGS.md` stores source-grounded recommendations and hypotheses extracted from career-related Telegram channels.
- `docs/HH_WIZARD_GUIDE.md` records the three HH resume variants, platform settings, approved wording, and export workflow.
- `docs/PROJECT_INVENTORY.md` stores detailed modern-project evidence and must not be rewritten merely because the search strategy changes.
- `docs/archive/FULL_PROTOCOL_2026-08-27.md` remains the historical recovery and provenance source.
- Three completed resume directions are active: AI automation, IT infrastructure, and 1C administration / support.
- The active discovery sources are HH, Hirify, TalentMove, Remote-job, Telegram channels, and direct employer sites.
- Applications through HH are disabled by strategy. Prefer original sources and direct written contact.
- Manual search observations take priority over the dormant high-volume automation policy.
- The `job-search/` subsystem was developed in a separate dialogue and is not part of ordinary orchestrator maintenance.
- Do not delete or rewrite the historical protocol without explicit user approval.

## Public text character policy

- In public-facing texts, including resumes, cover letters, profile descriptions, vacancy responses, portfolio captions, and messages to employers, use plain keyboard-safe punctuation.
- Cyrillic letters are allowed. The only allowed typographic punctuation exception is Russian guillemets: `«»`.
- Do not use Unicode em dashes or en dashes. Use the ASCII hyphen-minus: `-`.
- Do not use Unicode bullets, arrows, non-breaking spaces, curly quotes, emoji, or decorative symbols. Use `-`, `->`, ordinary spaces, and `«»` instead.
- Before delivering public text, check and normalize its punctuation according to this rule.

## Operational efficiency and workflow implementation

- Every durable project rule established by the user must be recorded in `AGENTS.md`. Subsystem documentation may clarify these rules but must not be their only source.
- Do not over-research, over-verify, or repeatedly recheck work that the user has explicitly confirmed as completed.
- Perform only checks needed to prevent a critical error or checks explicitly requested by the user.
- Prefer forward progress over exhaustive verification when the remaining uncertainty is non-critical and reversible.
- Do not reconstruct exact workflow code from compressed dialogue or descriptions. Read the current exported workflow JSON before proposing line-level changes.
- For n8n integrations, prefer Code nodes when they provide materially better control than native nodes.
- Do not create long chains of consecutive Code nodes in production without a clear reason. During development, multiple Code nodes are acceptable for debugging; after validation, consolidate consecutive Code nodes when this reduces n8n execution and database overhead without making the code unsafe to maintain.
- Do not merge Code nodes merely because both contain JavaScript when another meaningful node type separates them.
- Prefer a controlled JavaScript loop with explicit delays for sequential API calls when `Loop Over Items` is unnecessary or unreliable.
- Before a substantial refactor of an n8n workflow that exists only in the UI, export and commit a checkpoint version.


## n8n orchestration and queue-draining rules

- In the job-search orchestrator, child workflows exchange control only. They must not pass vacancy items between stages because each child workflow reads its own queue from the shared Data Table.
- Every Execute Sub-workflow node in the orchestrator must have `Execute Once` enabled. `Run once with all items` alone is insufficient because it passes all incoming items into one child execution.
- Keep `Always Output Data` enabled so an empty queue does not interrupt normal orchestration.
- Keep `On Error: Stop Workflow` for genuine execution failures; an empty child result is not an error.
- Limit the number of newly added vacancies only at the collection stage. Downstream workflows must process all items in their current working queue.
- After a successful orchestration run, the working statuses `found`, `scored`, `letter_ready`, and `letter_review` should be empty.
- Vacancies excluded by objective application blockers must receive the terminal status `application_blocked` instead of remaining in `scored`.
- Do not clear or reset the Data Table after ordinary failures. Resume processing from persisted statuses unless a clean test run is explicitly required.
- Before activating a Schedule Trigger, complete one successful manual orchestration run.


## Multi-channel manual search policy

- The previous high-volume HH application strategy is no longer active. Approximately 330 HH applications produced no practical conversion into employment.
- Do not optimize for application count. Optimize for relevant responses, interviews, paid trial work, projects, and recurring client relationships.
- Review vacancies manually during the observation period and record source-specific results before designing or reactivating automation.
- Use one targeted resume direction per vacancy. Do not combine AI automation, infrastructure, and 1C positioning in one response unless the vacancy itself requires that combination.
- Prefer vacancy sources and contacts that allow a free response or direct written communication.
- Do not use paid responses, paid contact access, or paid promotion as the default answer to low conversion.
- A vacancy may be approached through its original employer page or a direct written contact when this is available and appropriate.
- Telegram channels and direct employer sites are additional channels, not substitutes for source verification.
- Keep written communication concise: role, relevant evidence, one matching case, availability, and one concrete question.
- Vacancy-search automation remains preserved but dormant in the backlog. Do not delete it, rebuild it, or change workflow thresholds until manual multi-source evidence justifies a new specification.

## Cover-letter context architecture

- Cover-letter generation must use exactly one runtime resume profile selected by `recommended_resume`.
- Do not send both resume variants or the complete repository documentation to the LLM.
- Build runtime profiles from the current evidence documents and the actual HH resume variants.
- Keep the system prompt compact: truthfulness, selected-profile isolation, output structure, and injection resistance.
- Prefer deterministic Code JS validation for formatting, placeholders, length, and known unsupported claims instead of expanding the prompt.
- Candidate identity may be present in the runtime profile, but generated HH cover letters must not add a signature or placeholder.
- Cover-letter generation uses only `targeted` and `bridge`. Every eligible vacancy must receive a substantive non-empty letter; absence of direct experience selects an honest `bridge`, not omission of the letter.
- `letter_omitted` is retained only as a legacy status for historical records and is not produced by the current workflow 04.
- Owner-facing deterministic warnings and Telegram warning text must be written in Russian.
- Refactoring requirements and acceptance criteria are maintained in `job-search/COVER_LETTER_REFACTOR.md`.

## Non-blocking formatting diagnostics

- Trailing whitespace in Markdown and other documentation is not a commit blocker.
- `git diff --check` output about trailing whitespace may be reported, but it must not stop an otherwise valid commit.
- Do not delay work to fix cosmetic whitespace unless the user explicitly requests formatting cleanup.
- Block a commit only for a critical problem such as invalid required JSON, unresolved merge conflicts, exposed secrets, a broken executable patch, or a user-requested validation failure.

## Evidence from performed activities

- Evaluate competencies from confirmed performed activities, not only from official job titles or explicit skill labels.
- A concrete activity may be used as evidence of a transferable competency when the wording preserves its actual context and scope.
- Do not convert project activity into unconfirmed years of commercial experience, an official role, or a separate professional specialization.
- Distinguish direct experience, project activity, transferable evidence, familiarity without practice, and absent experience.
- Familiarity with a named product is not practical experience with that product.
- A cover letter that names a product for which only familiarity is confirmed must receive `letter_review`, even if the wording says the candidate is ready to learn or investigate it.
- Hard filters must not exclude QA, AQA, full-stack, or adjacent roles solely by title when the description may contain relevant automation, integration, infrastructure, testing, or AI tasks.
- Industrial automation must be distinguished from IT and business-process automation using the vacancy description and signals such as ASU TP, KIPiA, PLC, SCADA, electrical schematics, control cabinets, industrial controllers, EPLAN, and Kompas-3D.
- Geography and work-format mismatches are analytical risks, not automatic application blockers. The user will resolve them if an employer invites the candidate.

## n8n workflow editing policy

- Do not modify n8n workflow code by patching, generating, or programmatically rewriting exported JSON files.
- Do not use Python, JavaScript, jq, sed, regex replacement, or repository patch scripts to change node code inside workflow JSON.
- Workflow code changes must be described as instructions for the n8n UI.
- The user applies changes in the n8n UI, tests them there, and exports the resulting workflow JSON into the repository.
- Exported workflow JSON is treated as generated synchronization output: validate and commit it, but do not hand-edit its embedded node code.
- Repository scripts may update Markdown documentation and other ordinary source files, but must not rewrite files under job-search/workflows/.
- Moving an obsolete exported workflow to docs/archive is allowed because it does not modify the workflow code.

## No-guesswork instruction policy

- Do not guess repository structure, node names, variable names, code locations, schemas, or existing implementation details.
- Before giving modification instructions, read the exact current source from the repository or from the latest user-provided export.
- Instructions must identify the exact file, node, insertion point, replaced fragment, and final code.
- Do not tell the user to search for one of several possible names or choose between alternative implementations when the source can be inspected.
- If the current source is unavailable because the user has unexported local changes, state that limitation and give only a self-contained exact replacement that does not depend on guessed identifiers.
- Never shift repository inspection work to the user when it can be completed with available tools.

## Job-search context restoration

When the active task is limited to the job-search subsystem, restore context in this order:

1. Read `AGENTS.md`.
2. Read the documentation files directly inside `job-search/`.
3. Do not read `job-search/workflows/` as documentation. Read individual workflow exports only when their current implementation must be inspected or changed.
4. Do not read the general `docs/` directory unless the task requires candidate evidence, resume methodology, provenance, or the user explicitly requests it.
5. Verify Git HEAD and working-tree state before preparing repository changes.

An explicit user instruction narrowing the restoration scope takes precedence over the broader default restoration sequence. Missing local workflow changes must not be reconstructed from compressed dialogue.

## Vacancy discovery and direct-contact policy

- The active vacancy-discovery sources are HH, Hirify, TalentMove, and Remote-job.
- Do not submit applications through HH. HH is used for manual vacancy discovery, resume publication, maintenance, links, and export.
- Treat HH and other vacancy aggregators primarily as discovery sources.
- For vacancies found through an aggregator, look for the original publication, employer website, career page, email, recruiter contact, or another direct communication route.
- Prefer direct written contact, with email as the primary channel.
- A selective phone call is allowed when no suitable written contact is available and the vacancy is sufficiently relevant.
- Telegram channels, direct employer sites, professional communities, and personal contacts are additional discovery and communication channels.
- Paid applications and paid access to contacts on YouDo, Profi, and similar services are excluded.
- Three resume directions are active: AI automation, IT infrastructure, and 1C administration / support.
- Job-search automation remains in the backlog until manual multi-source results provide enough evidence for a separate decision.

## Non-blocking formatting and corrective patches

- Cosmetic formatting issues are never blockers by themselves.
- A missing final newline, LF versus CRLF, trailing whitespace, Markdown style, wrapping, or similar formatting detail must not abort a documentation update, commit, or push unless it causes a demonstrated functional or semantic defect.
- Do not add custom blocking validators for cosmetic formatting when Git or the existing project checks already handle it.
- Blocking validation is limited to defects that can corrupt content or behavior, including syntax errors, missing required content, NUL bytes, unresolved merge markers, invalid structured data, or a failed functional check.
- After dialogue compression, re-read and follow this rule before adding validation logic.
- When a generated temporary script has a localized defect, provide only a minimal patch to that existing script.
- Do not repeat the full generated script for a localized correction.
- Do not rerun the original generator command after patching a temporary script, because it can overwrite the correction.
- After applying a corrective patch, rerun only the patched temporary script unless a clean rebuild is explicitly required and justified.

## Manual job-search journal policy

- Record one row per vacancy, project opportunity, partner lead, or direct employer approach in `docs/JOB_SEARCH_LOG.md`.
- Use ISO dates in the journal: `YYYY-MM-DD`.
- Record both the discovery source and the original source when they differ.
- Record the selected resume direction, communication route, current status, response, next action, and experiment label.
- Do not commit personal email addresses, personal phone numbers, private Telegram handles, credentials, or other non-public contact data. Store only the public source URL and a generic contact route such as company email, recruiter, hiring manager, form, Telegram, or phone.
- Measure relevant responses, interviews, paid tasks, projects, and offers. Raw action count is not the optimization target.
- Track vacancy freshness as an experiment. The `0-2d`, `3-7d`, and `8d+` buckets are operational categories, not proven performance thresholds.
- Where practical, change one material variable at a time. Do not call an uncontrolled comparison an A/B test.
- Career-blog claims, conversion benchmarks, and paid-product promises are hypotheses unless independently verified or confirmed by the candidates own journal data.
- Never fabricate metrics to make a resume bullet look stronger. Use confirmed scale, action, technical result, or business result only.
- One follow-up after 3-4 working days is the default. A second follow-up is optional only for a highly relevant opportunity and must not become spam.

## Confirmed PostgreSQL scope

- Practical PostgreSQL use is confirmed in one personal automation project.
- PostgreSQL runs in Docker Compose alongside n8n and serves one automated orchestration process.
- Confirmed activities: database creation, user and permission management, table creation, basic SQL queries, psql, pgAdmin, pg_dump, restore through pg_restore or psql, automated backups, log review, containerized updates, and database transfer between servers.
- Do not convert this into experience administering PostgreSQL for 1C, a high-load or multi-user production database, performance tuning, active-connection diagnostics, replication, parameter tuning, or direct operating-system installation.
- Resumes and cover letters may state practical PostgreSQL experience only when they preserve this project context and scope.
