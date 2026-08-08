# Workflow

## Start

* 
**Domain Check**: The task begins by checking the pre-assigned domain displayed at the top of the task . The question's subject must strictly fall within that domain.


* **Task Claiming & Attempts**:
* Contributors start in a trial period capped at **5 attempts** (claimed and completed tasks) .


* Landing at least **1 Approved / Ready-to-Deliver (RTD)** task within those 5 attempts unthrottles the contributor, lifting all task volume caps permanently .





## Prompt Creation

* **Write the Prompt**:
* Write a clear, natural search prompt in self-contained English .


* Length must be **70 to 150 words**.


* Must genuinely require **3 or more distinct sources** across the web to answer.


* Pose a direct question; do not narrate research steps or name specific sources to open.




* **Write the Answer**:
* Provide exactly one correct answer formatted as a single short entity (Name, Place, Date, Number, Title, or Event) .


* Explanatory paragraphs or long-form answers are strictly prohibited.





## Validation

* 
**Pass Quality Checks**: Verify that the prompt passes all **8 mandatory quality rules** as `True` :


1. 
*Requires search* (cannot be answered from common knowledge).


2. 
*No shortcuts* (wording does not leak or hint at the answer).


3. 
*No external references* (self-contained; no "see table above" or attachments).


4. 
*Clear grammatical attachment* (unambiguous modifiers and pronouns).


5. 
*Question is specific* (constraints lead to exactly one entity).


6. 
*Claims are factual* (all premises and factual statements are true).


7. 
*Unique obvious answer* (one unambiguous answer clearly dominates).


8. 
*Answer is correct & verifiable* (accurate against primary sources).




* 
**Review Model Responses**: Test the prompt in your personal ChatGPT account to ensure the AI model genuinely fails by outputting an incorrect final answer .


* 
**Record Model Response**: Paste the model's full response, provide the Chat Share Link, and answer "Yes" to confirm the failure status .


* 
**Explain the Failure**: Write **2 to 4 sentences** describing specifically where the model went wrong and naming the correct answer .


* 
**Write the Golden Trajectory (GT)**: Document the step-by-step browsing path using the required 4-part structure (**Search → Fetch → Verify → Filter**) with direct deep-link URLs and exact on-page location anchors .


* 
**List Your Sources**: Provide direct deep links to at least **3 live, non-paywalled primary sources** that map directly to the steps in the Golden Trajectory .



## Submission

* **Submit the Task**:
* Complete the 8-item final submission checklist .


* Confirm the prompt fits the domain, answer is a short string, quality rules pass, genuine model failure is recorded, failure explanation is written, GT walks step-by-step, and sources map to primary evidence .


* Click submit to enter the automated quality checks and review queue.





## Review

* **Review 1 (R1)**:
* Reviewer verifies the prompt, answer, model failure, golden trajectory, and sources.


* 
**Edit + Approve (Yellow)**: Applied for fixable/cosmetic issues (typos, GT cleanup, missing page locations) when prompt and answer are sound; required for tasks with SQS score $\ge 3$ .


* 
**Send Back / Request Changes (Red)**: Applied for substantive broken tasks (domain mismatch, bad prompt, incorrect answer, unusable GT, false claims); permitted **only when SQS score is 1 or 2** .


* New and throttled reviewers must get sign-off in the sign-off channel before approving or sending back .




* **Review 2 (R2)**:
* A second check by experienced reviewers on R1-approved tasks prior to audit .


* Focuses strictly on major defects (broken URLs, unusable GT, incorrect answers, invalid prompts) .




* 
**Escalation**: Any task suspected of AI/LLM generation is escalated directly to project administrators rather than sent back .



## Completion

* **Ready-to-Deliver (RTD)**:
* Approved tasks clear R1, R2, and final project team audit to reach Ready-to-Deliver (RTD) status for customer delivery .




* **Payment**:
* Payment is issued **only for tasks that reach RTD status** (both during the trial and after being unthrottled).


* Tasks that do not reach RTD are not paid.


* Unthrottled contributors also receive a **$120 incentive** to set up a GPT-5.5 Pro Thinking Extended subscription for tasking.
