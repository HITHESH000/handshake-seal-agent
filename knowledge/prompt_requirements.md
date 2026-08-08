# Prompt Requirements

## Purpose

This file contains the official prompt-writing requirements for Project SEAL India.

## Information to Document

- Prompt length requirements
- Originality requirements
- Research requirements
- Single verifiable answer requirement
- Domain restrictions
- Quality requirements
- Common rejection reasons
- Reviewer expectations

## Source

Only record information extracted from the official Project SEAL India documentation located in the `training-docs` folder.

## Prompt Requirements

### Prompt Length

* Prompts must be between 70 and 150 words in length.
* The prompt should be long enough to carry all necessary constraints, but must not be an essay.
* The right length is similar to a typical BrowseComp prompt—neither a one-liner nor an essay.

### Originality Requirements

* Prompts must be completely original.
* Prompts must not be structurally similar to prompts previously submitted by the contributor.
* Prompts must not reuse the same combination of sources or the same correct answer.
* Prompts must not be copied from project examples.

### Research Requirements

* Must require 3 or more distinct sources to answer—it cannot be something findable in a single lookup.
* Must require digging across multiple sources on the web and cannot be answered from memory or common knowledge.
* Chains multiple facts so a strong AI model equipped with web search usually gets it wrong, while remaining solvable by a careful human researcher following the golden trajectory.
* Must be completely self-contained with no external references, attachments, tables, images, or prior conversation context.

### Single Verifiable Answer

* Must provide exactly one correct answer formatted as a short string—a single entity such as a Name, Place, Date, Number, Title, or Event.
* Explanatory or long-form paragraph answers are strictly prohibited.
* The answer must be verified by tracing it backward through primary and authoritative sources on the web.
* All constraints in the prompt combined must lock on to exactly one unique entity, proving no other plausible candidate fits every constraint.

### Domain Restrictions

* Prompts must fit the contributor's pre-assigned domain, which is displayed at the top of each task.
* Assigned subjects fall into 16 specific domains: Art, Business, Celebrities/Public Figures, Finance, Geography, Health & Medicine, History, Legal, Music, Politics, Science & Technology, Shopping, Sports, Travel, TV Shows & Movies, and Video Games.
* Prompts must lean into domain depth by targeting niche, well-documented corners rather than famous or common-knowledge facts.
* Subject mismatch with the assigned domain is grounds for task rejection.

### Quality Requirements

Every prompt must satisfy all 8 core quality rules (all must be rated True):

1. **Requires search:** Cannot be answered from common knowledge; requires web search.
2. **No shortcuts:** The prompt wording does not leak or strongly hint at the answer.
3. **No external references:** Self-contained without phrases like "in the table above", "see attached", or "as we discussed".
4. **Clear grammatical attachment:** Every clause attaches unambiguously to one referent without ambiguous pronouns or trailing relative clauses.
5. **Question is specific:** Removing the answer leaves constraints that point to exactly one entity.
6. **Claims are factual:** Every factual claim in the question is true (no false premises or misidentified entities).
7. **Unique obvious answer:** After research, one answer clearly dominates with no multiple equally valid candidates.
8. **Answer is correct:** Factually correct and verifiable against primary sources.

Additional requirements include:

* **Timelessness:** Any mutable fact (e.g., current record holders, prices, superlatives, counts) must be locked to a fixed date or dated snapshot.
* **Asking a Question:** Prompts must pose a natural question rather than narrating research steps or specifying exact sources to open.

### Common Rejection Reasons

* **Prompt Quality Failures:** Prompts that are not search-requiring, contain hints/shortcuts, include external references, have ambiguous grammatical attachment, are under-constrained/not specific, or contain false claims.
* **Domain Mismatch:** Prompts whose subject matter does not match the assigned domain.
* **Not Timeless:** Prompts containing mutable facts without a fixed date/snapshot.
* **Process Instructions:** Prompts that narrate step-by-step lookup steps or name exact sources to open instead of asking a question.
 No Real Model Failure:** Prompts where the model answers correctly, fails due to prompt ambiguity/underspecification, or fails only due to formatting/rounding differences.
 Invalid Answer Format:** Answers that consist of long explanations or paragraphs rather than a single short entity.
 *False Premises:** Questions built on an incorrect statement or misidentified entity.

  Reviewer Expectations

 R1 Reviewers

* Must verify the domain, prompt quality checks, timelessness, absence of process instructions, answer correctness, golden trajectory, and model failure validity.
* Send back (Red) for substantive errors (broken prompts, wrong answers, missing model failures, or incorrect GTs).
* Fix and Approve (Yellow) for minor issues (cosmetic wording, typos, formatting, minor GT structural fixes, or missing answer locations).
* Only reject/send back when giving an SQS score of 1 or 2 (rejecting a 3+ task is a review error).
* Every send-back comment must contain:

  1. Praise
  2. Specific tagged errors
  3. Concrete fix instructions

 R2 Reviewers

* Perform a second check on R1-approved tasks to verify that links open, sources are present in HTML, the final answer is correct with no other defensible options, model failures are valid, and the prompt is clean.
* Send back only for severe defects: invalid/ambiguous prompts, unusable GTs, incorrect answers, or competing defensible answers.
* Must not send back for URL count alone or search term answer leaks.

General Review Rules

* Flag every error with the correct error tag, even if a larger error is present.
* Include praise on every task, whether approved or rejected.
* Escalate suspected AI/LLM generation (e.g., templated GTs, empty/fake share links, fabricated citations) rather than sending it back.
