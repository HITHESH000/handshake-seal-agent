# FAQ

### What is Project Seal India?

Project Seal India is a project under Handshake AI where contracted contributors create challenging multi-hop web search questions and benchmark prompts designed to test, evaluate, and advance AI model capabilities in specialized domains.

### What are the confidentiality rules for Project Seal India?

Project Seal India is highly confidential. Contributors must not disclose the customer's name, the nature of the content, or share any screenshots or videos of the customer platform under any circumstances. Contributors who wish to list the role on a resume or LinkedIn profile must follow the Fellow Resume Policy.

### How does task access and trial unthrottling work?

Every contributor begins in a trial window capped at 5 attempts (claimed and completed tasks). To clear the trial and become unthrottled, a contributor must land at least 1 task that reaches Ready-to-Deliver (RTD) status within those 5 attempts. Once unthrottled, the task volume cap is permanently lifted.

### How are contributors paid for their work?

Payment is tied strictly to quality, not progress. Contributors are paid for every task that reaches Approved / Ready-to-Deliver (RTD) status, both during the trial window and after being unthrottled. Submitting a task does not guarantee payment, and tasks that do not reach RTD status are not paid.

### What incentive is offered to unthrottled contributors?

Contributors who obtain 1 RTD task and clear the trial receive a $120 incentive to set up a GPT-5.5 Pro Thinking Extended subscription to use while tasking.

### What are the official prompt-writing requirements?

A valid prompt must:

* Be written in clear, self-contained English as a natural search prompt.


* Be between **70 and 150 words** in length.


* Fit strictly within the pre-assigned domain displayed at the top of the task.
* Genuinely require **3 or more distinct web sources** across the web to answer.


* Pose a direct question rather than writing step-by-step lookup instructions or naming exact sources to open.


* Be completely original and not reused or copied from project examples.



### What formatting and accuracy rules apply to the answer?

* The answer must be a single, short string representing a specific entity (such as a name, place, date, number, title, or event).
* Explanatory paragraphs or long-form descriptions are strictly prohibited.


* The answer must be printed on a live, trustworthy web page where it can be highlighted in plain text.


* Mental math or arithmetic derivation of the final answer is prohibited; any numeric answer must be read directly off the source page.



### What are the 8 quality checks every task must pass?

All 8 rules must evaluate to `True` for a task to pass:

1. 
**Requires Search**: Cannot be answered from common knowledge or single lookups.


2. 
**No Shortcuts**: Wording does not leak, reveal, or strongly hint at the answer.


3. 
**No External References**: Self-contained with no mentions of attachments, images, or "table above".


4. 
**Clear Grammatical Attachment**: Modifiers and pronouns attach unambiguously to one referent.


5. 
**Question is Specific**: Constraints narrow the pool down to exactly one entity.


6. 
**Claims are Factual**: Every factual statement and premise in the prompt is verified true.


7. 
**Unique Obvious Answer**: After research, one unambiguous answer clearly dominates.


8. 
**Answer is Correct**: Factually accurate and verifiable against primary sources.



### What defines a genuine model failure?

A genuine model failure occurs when an AI search model (e.g., ChatGPT with web browsing) tests a sound prompt and produces a confident, incorrect final answer. A failure caused by an ambiguous or underspecified prompt, an error in reference answer, a formatting difference, or a correct model refusal does not count as a model failure.

### What is a Golden Trajectory (GT) and how must it be formatted?

The Golden Trajectory is the ideal step-by-step browsing sequence a person takes to reach the correct answer. Every constraint in the prompt must have its own step  formatted as:

* 
`Step X: Search: "<exact query>" and <navigation path>` 


* `Step Y: Fetch: <URL> to find <answer> (at specific location on page)`
* 
`Step Z: Verify: confirms <specific constraint from prompt>` 


* 
`Step W: Filter: <reason how step narrows candidate answers>` 



Every step must contain a direct deep-link URL openable in an incognito tab and specify the exact location on the page (paragraph, table row, section) where the fact lives.

### Which sources are prohibited for key verification?

Prohibited sources include:

* Archive.org 


* Wikipedia for key/decisive verification 


* Audio or video content (e.g., YouTube, Spotify) 


* Search-engine result pages or spatial-only Google Maps/Street View 


* User-generated forums as sole factual sources 


* Cached snapshots when live pages contradict them 


* Paywalled sources inaccessible to reviewers 



### When should a reviewer reject (send back) a task versus edit and approve it?

* **Send Back (Red)**: Assigned only when a task is substantively broken (failing quality checks, wrong answer, unusable GT, false premises, or unverified sources) **and** receives an SQS score of 1 or 2.
* **Edit & Approve (Yellow)**: Required for fixable, non-substantive issues (typos, grammar, minor GT ordering, missing page location anchors, date formatting, or link sorting) on tasks receiving an SQS score of 3 or higher. Rejecting an SQS 3+ task is a review error.



### What is the protocol if AI/LLM usage is suspected in a task?

If a task shows signs of being AI-generated (e.g., generic GT boilerplate, unreplaced placeholders like `[Acquiring Company]`, empty/deleted ChatGPT share links, or pasted LLM meta-commentary), reviewers must **escalate** the task to project administrators rather than sending it back. Escalation protects reviewer pay and flags policy abuse.
