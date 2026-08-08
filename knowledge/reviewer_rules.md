# Reviewer Rules

## Approval Criteria

* **Default Action:** R1 reviewers should default to *Edit + Approve* whenever the prompt and answer are sound, fixing small issues themselves instead of bouncing the task back.
* **Core Conditions for Approval:** A task is approvable if it has a valid prompt, a correct answer, and at least one verifying URL.
* **Fixable (Yellow) Issues:** Reviewers must correct minor issues themselves and approve the task rather than sending it back. These include:

  * Minor grammar, spelling, punctuation, or light wording fixes in the prompt, answer, or Golden Trajectory (GT).
  * Minor GT imperfections where steps are slightly unclear or out of order but logic is sound and reaches the correct answer.
  * Missing page/answer locations that the reviewer can manually add.
  * Formatting adjustments to the answer (e.g., date formats) where the substance is correct.
  * Source list cleanups, such as reordering links to match the GT, fixing labels, removing duplicate links, or fixing link-annotation tags.
  * Reclassified items (per latest policy): invalid ChatGPT share links, mis-marked model failures, or missing model failures where the reviewer can restore/verify the runs themselves.
* **SQS Threshold:** Edit and approve tasks when assigning an SQS score of 3 or above.

## Rejection Criteria

* **Substantive (Red) Issues:** Reviewers must send a task back only when it is substantively broken and the contributor must fix it. Reasons include:

  * **Domain Mismatch:** The prompt subject does not fit the assigned domain.
  * **Prompt Quality Failures:** Prompts that fail core rules (not search-requiring, contain shortcuts/hints, include external references like "see table above", have ambiguous grammatical attachment, are under-constrained/not specific, or contain false claims).
  * **Not Timeless:** The answer could change over time and lacks a fixed date/snapshot.
  * **Process Instructions:** Prompts that narrate research lookup steps or name exact sources to open instead of posing a question.
  * **Incorrect/Invalid Answer:** Answers that are factually wrong, unverifiable, or yield multiple defensible candidates.
  * **Unusable Golden Trajectory:** GTs that are reverse-engineered, incorrect, missing URLs, or missing exact source locations.
  * **Invalid Arithmetic:** Arithmetic used as the sole reason the model fails or used to construct an answer that cannot be read directly from a URL.
* **SQS Score Restriction:** Tasks must **only** be rejected/sent back when given an SQS score of 1 or 2. Rejecting a task with an SQS score of 3+ is considered a review error.
* **Mandatory Feedback Structure:** Reviewers cannot hit "Request changes" until tagged feedback is present. Every send-back comment must contain:

  1. Praise for what the contributor did well.
  2. Specific named errors, each tagged with the correct error tag.
  3. Concrete, in-depth guidance detailing how to fix the errors.
* **Forbidden Rejection Reasons:**

  * Tasks must **never** be sent back for URL count alone (needs at least one valid URL).
  * R2 reviewers must **not** send tasks back for search term answer leaks or GT leaks.

## Red Flags

* **AI/LLM Generation Signals:** If a task appears AI-generated, reviewers must **escalate** it to the project team instead of simply sending it back. Signs include:

  * Golden Trajectory or context reading like templated AI text (e.g., phrases like "Here's the version in the format you requested").
  * ChatGPT share links that are empty, deleted, identical across different runs, contain instant answers with no reasoning, or link to other bots.
  * Placeholder/template GTs (e.g., `[exact page confirm before submitting]`).
  * Fabricated citations or answers provided without supporting sources.

## Quality Checks

Reviewers verify tasks against the 8 core prompt rules:

1. **Requires Search:** Question cannot be answered from memory/common knowledge; requires web search.
2. **No Shortcuts:** Prompt wording does not leak or hint at the answer.
3. **No External References:** Prompt is self-contained with no attachments or "see above" context.
4. **Clear Grammatical Attachment:** Clauses attach clearly without ambiguous referents.
5. **Question is Specific:** Prompt constraints narrow down to exactly one entity.
6. **Claims are Factual:** Every statement in the question is true.
7. **Unique Obvious Answer:** One dominant answer exists with no competing candidates.
8. **Answer is Correct:** Factually correct and verified against primary sources.

Reviewers also verify that:

* Every URL in the GT and source list opens, is live, and matches the figures cited.
* The GT follows the 4-step format (Search → Fetch → Verify → Filter) with exact page/text locations provided.
* Model failures are genuine (model searched and reached a wrong answer, not caused by prompt ambiguity or formatting/rounding differences).

## Validation Process

1. **Review Pipeline:**

   * **Review 1 (R1):** The primary reviewer evaluates the prompt, answer, model failure, GT, and sources; edits + approves or tags errors and sends back.
   * **Review 2 (R2):** Experienced reviewers perform a second check on R1-approved tasks with a tighter bar and narrow send-back criteria before audit.
   * **Audit:** Project team audits approved tasks before final customer delivery.

2. **R2 Specific Restrictions:**

   * R2 reviewers check that links open, sources are present in HTML, answer is unique/correct, model failure is valid, and prompt is clean.
   * R2 send-backs are strictly limited to invalid/ambiguous prompts, unusable GTs, wrong answers, or alternative defensible answers.
   * Reviewers must not R2 their own tasks.
   * R2 send-backs must be logged in the daily send-back thread (tagging the R1 reviewer, Task ID, issue summary, and action).

3. **Sign-Off Requirements:** New and throttled reviewers must post in the sign-off channel and receive sign-off before approving or sending back tasks.

4. **Error Tagging:** Reviewers must flag *every* error found with its specific error tag, even if a larger error already requires the task to be sent back.

