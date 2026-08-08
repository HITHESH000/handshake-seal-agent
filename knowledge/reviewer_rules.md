# Reviewer Rules

## Approval Criteria

* Reviewers should default to edit + approve whenever the prompt and answer are sound, fixing small fixable issues themselves instead of bouncing the task back.


* Edit + approve applies when a task has a valid prompt, a correct answer, and at least one verifying URL.


* Fixable "Yellow" issues that must be edited by the reviewer and approved include:
* Cosmetic wording, grammar, spelling, and punctuation in the prompt, answer, or Golden Trajectory (GT).


* Minor GT imperfections where steps are slightly unclear or out of order but logic is sound and reaches the correct answer.


* Adding missing answer locations/anchors or tidying GT steps.


* Pulling a missing URL from the Verification URLs block into the GT.


* Answer formatting clean-ups (e.g., date formats) where substance is correct.


* Source-list tidy-ups (reordering links to match GT, fixing labels, removing obvious duplicates, correcting link-annotation tags).


* Invalid ChatGPT share link (reclassified to edit + approve).


* Invalid model failure or no model failure present (reclassified to edit + approve as long as prompt and answer are good).




* Approve tasks by clicking the Approve button in the bottom-right action panel.



## Rejection Criteria

* A task must be sent back (RED) with specific tagged comments when substantive issues exist that the fellow must fix:


* 
**Domain Mismatch**: Prompt subject doesn't match the assigned domain.


* 
**Prompt Quality Failure**: Prompt is not search-requiring, contains shortcuts/hints, has external references ("see table above"), ambiguous grammatical attachment, not specific (multiple entities fit), contains a false/incorrect claim, or has no unique obvious answer.


* 
**Not Timeless**: Answer could change over time and no fixed date/snapshot is given.


* 
**Process Instructions**: Prompt narrates research steps or names exact sources to open instead of posing a question.


* 
**Incorrect/Invalid Answer**: Fellow's answer is factually incorrect, or there are other defensible answers.


* 
**No Genuine Model Failure**: Model didn't genuinely fail, or no valid failure can be restored.


* **Unusable Golden Trajectory**: GT is completely wrong, missing exact deep-link URLs, missing exact page locations, reverse-engineered from the answer, templated/LLM-written, uses math to construct the final answer, or mismatched with source list/answer.
* 
**Unverifiable Answer**: Answer cannot be verified from provided primary sources.




* 
**SQS Score Requirement**: Reviewers may reject a task **only when assigning an SQS score of 1 or 2**. Rejecting a task given an SQS score of 3 or above is a review error.


* Do **not** send back for URL count alone (needs at least one valid URL to be approvable).


* At Review 2 (R2), do **not** send back for answer leaks in GT/search terms or anything not on the strict R2 send-back list.



## Red Flags

* 
**Suspected LLM Usage**: If a task looks AI-generated, reviewers must **escalate** it rather than sending it back (escalation flags it for the project team and protects reviewer pay). Common tells include:


* GT or "additional context" that reads like AI (templated boilerplate, phrases like *"Here's the version in the format you requested"*).


* ChatGPT share links that are empty, deleted, or identical across "different" runs.


* Instant answers with no reasoning, or links from other bots.


* Placeholder/template GTs (e.g., `[exact page confirm before submitting]`).


* Fabricated citations or answers with no supporting source.




* 
**Plagiarism**: Reusing prompt structures, sources, or answers from project examples is prohibited.


* 
**Calculated Math**: Reject if the answer only exists as a computed value or if arithmetic caused the model failure.



## Quality Checks

* Reviewers must verify the entire pipeline:
1. Prompt fits assigned domain and is clear, self-contained, timeless, specific, and search-requiring.


2. Answer is a single short entity, factually correct, and verified with no contradicting sources.


3. Model failure is genuine and verified (restoring/verifying model runs where possible).


4. Golden Trajectory follows the required 4-part step format (**Search → Fetch → Verify → Filter**) with exact deep-link URLs and exact on-page locations.
5. Sources are live, non-broken, accessible in an incognito tab, non-paywalled, primary/authoritative, and match GT links.



## Validation Process

* **Feedback Rules for Send-Backs**: Reviewers sending a task back must structure comments as:
1. 
**Praise**: What the fellow did well.


2. 
**What's wrong**: Name each error specifically, tagged with the correct error tag.


3. 
**How to fix it**: Concrete, in-depth guidance the fellow can act on.




* Feedback must contain tagged errors for the **Request changes** button to become enabled.


* 
**Tagging Requirement**: Flag every error found with the correct error tag, even when a larger top-level error already sinks the task.


* 
**Praise Rule**: Include praise on every single task reviewed, whether approved or rejected.


* 
**Sign-off for New & Throttled Reviewers**: New and throttled reviewers must request and receive sign-off in the sign-off channel before approving or sending back a task. Format:
`@[signer] | Task ID: [xxxx] | Review #[X] | SQS Score [X] | [cite_start]About to Approve/Send Back [one-sentence reason]`.


* **Review 2 (R2) Norms**:
* R2 is a second check on R1-approved tasks before audit/delivery.


* Never R2 your own tasks.


* Prioritize new reviewers and lowest-scoring reviewers.


* Log R2 send-backs in the daily send-back thread (tag R1 reviewer, task ID, brief summary, decision).
