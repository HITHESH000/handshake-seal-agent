# Validation Process

## Purpose

* 
**Quality Gatekeeping**: Reviewers act as the gatekeepers of quality to ensure every task submitted by a fellow passes through systematic verification before it can be delivered to the customer.


* **Maintaining High Standards**: The process verifies that tasks meet the required quality bar, confirming that prompts, answers, model failure justifications, golden trajectories, and source links are completely sound and defensible.

## Validation Steps

1. **Task Submission & Automated Quality Checks**: The fellow finishes and submits the task, which must clear automated quality checks before entering the review queue.
2. **Review 1 (R1)**: A reviewer verifies the whole task (prompt, answer, model failures, golden trajectory, and sources) and either edit + approves the task or sends it back to the fellow.
3. **Sign-off (for New & Throttled Reviewers)**: New and throttled reviewers must request and receive sign-off in the sign-off channel prior to approving or sending back a task. The required sign-off format is `@[signer] | Task ID: [xxxx] | Review #[X] | SQS Score [X] | [cite_start]About to Approve/Send Back [one-sentence reason]`.


4. **Review 2 (R2)**: A second, more experienced reviewer re-checks R1-approved tasks before they move forward to audit. R2 applies a tighter bar focused strictly on catching real defects using a narrow set of valid send-back reasons.


5. **Project Team Audit**: The project team audits approved tasks and moves those that pass to Ready-to-Deliver (RTD) status for customer delivery. Audit send-backs are tracked and fed back to reviewers.



## Reviewer Checks

* 
**Domain Check**: Reviewers confirm that the prompt's subject strictly matches the pre-assigned domain shown at the top of the task.


* **Prompt Quality Checks**: Reviewers verify that the prompt satisfies all core rules (requires web search, contains no shortcuts/hints, has no external references, has clear grammatical attachment, resolves to a single specific entity, contains only true claims, and has a unique obvious answer).
* **Timelessness Check**: Reviewers ensure the answer cannot change over time or is locked to a fixed date or dated snapshot.
* 
**Process Instructions Check**: Reviewers confirm the prompt poses a direct question rather than narrating research steps or naming exact sources to open.


* 
**Answer Checks**: Reviewers verify that the answer is factually accurate, formatted as a single short entity (not a paragraph or explanation), verified against primary sources, and has no competing defensible answers.


* **Model Failure Verification**: Reviewers confirm the model genuinely failed against the verified reference answer, restoring and verifying model runs themselves where needed.
* **Golden Trajectory (GT) Checks**: Reviewers trace each step to ensure it follows the required format (`Search → Fetch → Verify → Filter` / `search → source → what to verify`), contains direct deep links openable in an incognito tab, specifies exact on-page location anchors (paragraph, table row, section), is derived forward from clues rather than reverse-engineered, contains no arithmetic derivation of the final answer, and uses no templated LLM boilerplate.
* **Verification Sources Checks**: Reviewers check that at least 3 live, non-broken, non-paywalled, authoritative primary links are provided matching the GT steps, evaluating them against link annotation attributes (Trustworthy, Paywall, Geographical reach, Govt website, Relevance).
* **R2 Validation Checks**: R2 reviewers specifically verify that every link opens and text highlights in HTML, the final answer has no contradicting sources, the full GT traces end-to-end to validate the model failure, and the prompt is clean and free of factual errors.

## Quality Verification

* 
**Automated Quality Checks**: Submissions pass automated checks that screen for issues such as full-sentence answers instead of short entities or unanchored timelessness terms.


* **8 Quality Rules (All Must Be True)**:
1. 
*Requires search*: Cannot be answered from common knowledge.


2. 
*No shortcuts*: Prompt wording does not leak or hint at the answer.


3. 
*No external references*: Prompt is self-contained with no references to attachments, images, or "tables above".


4. *Clear grammatical attachment*: Modifiers and pronouns attach unambiguously to one referent.
5. *Question is specific*: Removing the answer leaves constraints pointing to exactly one entity.
6. *Claims are factual*: Every factual claim and premise in the prompt is verified true.
7. *Unique obvious answer*: After research, one unambiguous answer clearly dominates.
8. *Answer is correct*: Factually accurate and verifiable against primary sources.


* **System Quality Score (SQS)**:
* Reviewers assign an SQS score to every task reviewed.
* SQS 1 or 2 indicates substantive/major errors requiring the task to be sent back.
* SQS 3, 4, or 5 indicates a sound prompt and answer with minor/fixable issues requiring reviewer edit and approval.




* **Source Attribute Verification**: Sources are judged across five specific attributes: Trustworthy, Paywall, Geographical reach, Govt website, and Relevance.
* **Escalation Protocol for AI/LLM Usage**: If a task displays tells of AI generation (generic GT boilerplate, unreplaced placeholders like `[Acquiring Company]`, empty or deleted ChatGPT share links, or pasted LLM meta-commentary), reviewers escalate the task directly to project administrators rather than sending it back.

## Approval Criteria

* **Ready-to-Deliver (RTD)**: A task reaches Ready-to-Deliver (RTD) status once it clears R1, R2, and final project team audit.
* **Edit & Approve Rule (Yellow Issues / SQS $\ge 3$)**:
* Reviewers must default to edit + approve whenever the prompt and answer are sound.


* Baseline criteria for Edit + Approve: Valid prompt + correct answer + at least one verifying URL.


* Issues that must be fixed in-review by the reviewer and approved include:
* Typos, grammar, spelling, punctuation, or light wording cleanups in the prompt, answer, or GT.
* Minor GT imperfections where steps are slightly unclear or out of order but logic is sound and reaches the correct answer.


* Adding missing page location anchors/locations to GT steps.


* Pulling missing URLs from the Verification URLs block into the GT.


* Formatting cleanups of the answer (e.g., date formatting) where substance is correct.


* Source list tidy-ups (reordering links to match GT, fixing labels, removing obvious duplicates, or correcting link-annotation tags).
* Invalid ChatGPT share links, invalid model failure tags, or missing model failures (reclassified to edit + approve as long as prompt and answer are sound).


* Rule: Rejecting a task given an SQS score of 3 or above is a review error. Reviewers must click the Approve button in the action panel to move the task forward.


* **Rejection / Send-Back Criteria (Red Issues / SQS 1 or 2)**:
* Reviewers may reject (send back) a task **only when assigning an SQS score of 1 or 2**.
* Substantive Red issues requiring a send-back include:
* Domain mismatch.


* Prompt failing any core quality check (not search-requiring, shortcuts/hints, external references, ambiguous grammatical attachment, under-constrained/multiple entities fit, false premise/factual error, no unique obvious answer).
* Prompt failing timelessness.


* Prompt containing process instructions.


* Incorrect, long-form, unverifiable, outdated, or contradicted answer.


* Lack of genuine model failure (or failure caused by prompt ambiguity rather than model stump).


* Unusable Golden Trajectory (completely wrong, missing exact deep-link URLs, missing exact page locations, reverse-engineered, templated/LLM-written, computed via arithmetic, or mismatched with answer/sources).
* Verification links that fail to support the answer (untrustworthy sources, broken links, or paywall/geographical blocks preventing verification).




* Send-Back Feedback Requirement: Every send-back must contain specifically tagged errors and follow a strict three-part feedback structure: 1. Praise, 2. What's wrong (specifically named and tagged), 3. How to fix it (concrete guidance).
