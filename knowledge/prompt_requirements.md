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

# Prompt Requirements

## Prompt Length

* The prompt must be between **70 and 150 words** in length.


* It must be long enough to carry all constraints without being an essay or a one-liner.



## Originality Requirements

* Prompts must be completely original and written in your own words.


* Prompts must not be structurally similar to prompts you have submitted previously.


* Prompts must not reuse the same combination of sources or the same correct answer.


* Copying a question, its sources, or its answer from project examples is strictly prohibited, counts as plagiarism, and results in immediate off-boarding.



## Research Requirements

* Prompts must be written in English as a natural search prompt that someone would type into a search engine.


* Prompts must genuinely require **3 or more distinct sources** across the web to answer, rather than being findable in a single lookup.


* Prompts must chain multiple facts and constraints together to lead to one obscure entity.


* Questions must not be answerable from memory or common knowledge alone.


* Difficulty is essential: constraints should be chained so that a strong search-enabled AI usually fails, while remaining solvable by a careful human researcher.


* Prompts must pose a direct question rather than narrating research steps or naming specific sources to look up.



## Single Verifiable Answer

* The prompt must lead to exactly **one short, verifiable answer** consisting of a single entity such as a name, place, date, number, title, or event.


* Explanatory, long-form, or paragraph answers are strictly prohibited.


* The answer must have no reasonable alternative or competing candidate.


* The answer must be independently verifiable against primary or official web sources before submission.


* The answer must be explicitly printed in plain text on a trustworthy page where it can be highlighted; it must never be calculated, added up, or worked out in your head.



## Domain Restrictions

* Prompts must strictly fit within the specific pre-assigned domain displayed at the top of the task.


* The 16 allowed domains are: *Art, Business, Celebrities/Public Figures, Finance, Geography, Health & Medicine, History, Legal, Music, Politics, Science & Technology, Shopping, Sports, Travel, TV Shows & Movies, Video Games* .


* Prompts should lean into niche, well-documented corners of the assigned domain rather than famous or common facts .



## Quality Requirements

Every prompt must pass all **8 mandatory quality rules** as `True`:

1. 
**Requires Search**: Cannot be answered from common knowledge; requires web search.


2. 
**No Shortcuts**: Wording does not leak, strongly hint at, or reveal the answer.


3. 
**No External References**: Self-contained with no references to tables above, attachments, images, or prior conversations.


4. 
**Clear Grammatical Attachment**: Every clause attaches clearly to one referent with no ambiguous pronouns or trailing modifiers.


5. 
**Question is Specific**: Removing the answer leaves constraints pointing to exactly one entity.


6. 
**Claims are Factual**: Every factual statement and premise in the prompt is entirely true.


7. 
**Unique Obvious Answer**: After thorough research, one unambiguous answer clearly dominates.


8. 
**Answer is Correct**: Answer is factually accurate and verifiable against primary sources.



* 
**Timelessness**: Any mutable facts (superlatives, current title holders, prices, live counts) must be locked to a fixed date or dated snapshot.



## Common Rejection Reasons

* Prompt fails any core quality check (e.g., common knowledge, leaks answer, ambiguous grammar, or not specific).


* Subject matter does not match the assigned domain.


* Prompt contains a false premise, incorrect factual claim, or misidentified entity.


* Prompt is not timeless and uses mutable facts without specifying a fixed date or snapshot.


* Prompt includes process instructions that narrate lookup steps or explicitly name sources to open.


* Prompt is plagiarized, structurally identical to prior submissions, or copies project examples.


* Absence of a meaningful model failure (e.g., the AI model answered correctly, or failed due to an ambiguous/underspecified prompt) .


* Answer relies on calculated math rather than reading a printed value directly from a primary source.



## Reviewer Expectations

* Reviewers must evaluate the prompt, answer, model failure justification, golden trajectory, and source links.


* Issues are categorized as **RED (Send back)** for substantive errors or **YELLOW (Edit & Approve)** for fixable formatting/cosmetic errors .


* Reviewers may send back a task (RED) only if they assign an **SQS score of 1 or 2**.


* Rejecting a task with an **SQS score of 3 or higher** is a review error; reviewers must edit yellow issues themselves and approve.


* Reviewers must tag every error found, even when a larger error already sinks the task.


* Reviewers must include genuine praise on every task review, whether approving or rejecting.


* Send-back comments must strictly follow a three-part structure: 1. Praise, 2. What's wrong (specifically tagged), 3. Concrete guidance on how to fix it .


* Reviewers must escalate suspected AI/LLM generation directly to project admins rather than sending it back.
