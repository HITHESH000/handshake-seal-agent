# Project Guidelines

## Purpose

This document contains the official rules, notes, and important guidance for Project SEAL India.

## Sections

- Prompt requirements
- Answer requirements
- Reviewer expectations
- Submission workflow
- Validation process

## Notes

Only include information taken from official project documentation.

Do not add personal opinions or unverified rules.

Whenever the project documentation changes, update this file.


# Project Overview

## Purpose

* 
**Building High-Quality Evaluation Data**: Handshake AI serves as a data partner for AI labs to create high-quality data that advances AI capabilities across specialized domains.


* 
**Driving Access, Fairness, and Innovation**: Contracted contributors build data designed to improve the access, fairness, and technical innovation of AI search and reasoning models.



## Objectives

* 
**Create Hard, Multi-Hop Web Search Prompts**: Develop complex, self-contained questions requiring information from **3 or more distinct web sources** that cannot be answered from memory alone.


* 
**Stump Advanced Search-Enabled AI Models**: Craft questions difficult enough to cause strong AI models equipped with web search to reach an incorrect final answer, while remaining solvable by a careful human researcher.


* 
**Pinpoint Unique, Verifiable Answers**: Ensure each prompt narrows down to exactly **one short, verifiable answer** (a specific entity) with no reasonable alternative answers or false premises.


* 
**Provide Defensible Golden Trajectories**: Document the step-by-step browsing path and authoritative primary sources required to solve the question, establishing a gold-standard benchmark for customer delivery.



## Main Tasks

1. **Check Your Domain**: Verify that the question subject falls strictly within the pre-assigned domain (selected from 16 domains such as *Legal, History, Geography, Science & Tech, Sports, TV Shows & Movies, etc.*).
2. **Write the Prompt**: Draft a clear, natural search prompt in self-contained English between **70 and 150 words** that requires chaining multiple constraints across 3+ sources.
3. **Write the Answer**: Provide a single short entity answer (e.g., a name, place, date, number, title, or event) without long explanatory paragraphs.
4. **Pass Quality Checks**: Verify the prompt satisfies all **8 mandatory quality rules**:
* 
*Requires search* (cannot be answered from common knowledge).


* 
*No shortcuts* (wording doesn't leak or hint at the answer).


* 
*No external references* (no "see table above" or attachments).


* 
*Clear grammatical attachment* (unambiguous modifiers and pronouns).


* 
*Question is specific* (constraints lead to exactly one entity).


* 
*Claims are factual* (all premises in the question are true).


* 
*Unique obvious answer* (one answer clearly dominates).


* 
*Answer is correct & verifiable* (matches primary sources).




5. 
**Review Model Responses**: Test the prompt in your personal ChatGPT account to confirm the AI model genuinely fails by outputting an incorrect final answer.


6. **Record Model Response**: Copy and paste the model's full response, provide the Chat Share Link, and confirm the failure status.
7. **Explain the Failure**: Write 2 to 4 sentences identifying the correct answer and explaining specifically where the model went off track.
8. **Write the Golden Trajectory (GT)**: Detail the precise browsing path using the required 4-part structure (**Search → Fetch → Verify → Filter**) with direct deep links and exact on-page locations.
9. **List Sources**: Provide deep links to at least 3 live, non-paywalled primary sources mapping directly to each step in the Golden Trajectory.
10. **Submit for Review**: Complete the final checklist and submit the completed task into the review queue.

## Key Concepts

* 
**Ready-to-Deliver (RTD)**: An approved task that has cleared review and is ready for customer delivery; payment is issued only for tasks reaching RTD status.


* 
**Trial Period & Attempts**: Contributors start with a trial limit of **5 attempts** (claimed and completed tasks) and must land **1 RTD task** within those 5 attempts to clear the trial.


* **Unthrottled Status**: Reached after obtaining 1 RTD task during the trial; lifts all task volume caps, unlocks incentive eligibility, and provides a $120 incentive for setting up a GPT-5.5 Pro Thinking Extended subscription.
* **Meaningful Model Failure**: Occurs when an AI model searches, reasons, and confidently outputs a wrong final answer due to the complexity of the research chain (not due to prompt ambiguity, typos, rounding/formatting differences, or correct refusals).
* **Golden Trajectory (GT)**: The ideal step-by-step browsing sequence a person takes to solve the prompt from scratch; it requires exact deep-link URLs, specific location anchors (e.g., paragraph number, table row), and logical filtering explanations.
* **Review Pipeline (R1, R2, Audit)**:
* 
*Review 1 (R1)*: Initial review verifying prompt, answer, model failure, GT, and sources.


* *Review 2 (R2)*: Second-level review by experienced reviewers with a tight focus on catching true defects (unusable GT, incorrect answers, invalid prompts).
* *Audit*: Final audit before tasks are delivered to the customer.


* **Red vs. Yellow Issues**:
* *RED (Send Back)*: Substantive errors (broken prompt, incorrect answer, no real model failure, unusable GT) requiring the task to be sent back for changes; applies only when SQS score is 1 or 2.
* *YELLOW (Edit & Approve)*: Fixable in-review issues (formatting, typos, minor GT cleanup) where the reviewer fixes the issue directly and approves the task; mandatory for tasks with SQS score of 3 or higher.ucted by experienced reviewers to verify links, answers, prompts, and model failures before audit and delivery .


* 
**Audit**: Final project team checks before delivery to the customer .
