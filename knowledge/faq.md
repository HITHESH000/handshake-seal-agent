# FAQ

### What is Handshake AI?

Handshake AI is a trusted data partner for leading AI labs that hand-picks individuals to create data that advances AI in specific domains. Contributors are officially contracted with Handshake, not directly with the AI lab.

### What is Project SEAL India?

Project SEAL India is a project where contributors write challenging, multi-constraint search questions that cannot be answered from memory and require digging across multiple web sources. Every question must have one short, verifiable answer that stumps a strong AI model allowed to search.

### What are the confidentiality rules for Project SEAL India?

Under no circumstances should contributors disclose the customer's name, the nature of the content, or share any screenshots or videos of the customer platform.

### How does the trial phase work compared to being unthrottled?

* **Trial:** Access is capped at 5 attempts to prove you can hit the quality bar.
* **Unthrottled:** Once you land 1 Ready-to-Deliver (RTD) task within your first 5 attempts, the task limit is lifted for good, allowing you to take unlimited tasks and become eligible for incentives.

### How do contributors get paid?

Payment is tied strictly to quality, not progress. Contributors are paid for every task that reaches the Approved / Ready-to-Deliver (RTD) stage. Tasks that do not reach RTD (unapproved or rejected tasks) are not paid.

### What incentive is provided upon getting unthrottled?

Unthrottled contributors receive a $120 incentive to set up a GPT-5.5 Pro Thinking Extended subscription to use while tasking.

### What is a "Ready-to-Deliver (RTD)" task?

An RTD task is an approved task that has passed review and quality checks; only these count toward clearing the trial and getting paid.

### What is a "Meaningful Model Failure"?

A meaningful model failure occurs when the model reaches an incorrect final answer due to the complexity of the prompt, rather than due to prompt ambiguity, underspecification, or formatting issues.

### What are the prompt length and language requirements?

Prompts must be written in clear, self-contained English and be between 70 and 150 words long.

### What type of answer is required for a prompt?

The answer must be a single short entity—such as a Name, Place, Date, Number, Title, or Event. Explanatory or long-form paragraph answers are strictly forbidden.

### What is the Golden Trajectory (GT)?

The Golden Trajectory is the ideal step-by-step browsing sequence a person would take to reach the correct answer from scratch. It must follow a strict 4-part format for every step:

**Search query and navigation path → Fetch URL and exact location → Verify constraint → Filter explanation.**

### What causes a Golden Trajectory to be rejected?

Top causes for GT rejections include:

* Missing deep-link URLs or missing exact source locations (the #1 rejection cause).
* Reverse-engineering the steps backward from the answer instead of deriving them forward.
* Using LLMs or AI tools to write the GT.
* Relying on manual arithmetic to construct the final answer instead of reading it directly from a source.
* Mismatched figures or URLs between the GT, answer, and source list.

### What are the 8 quality checks every task must pass?

1. **Requires search:** Cannot be answered from common knowledge or a single lookup.
2. **No shortcuts:** Wording does not leak or hint at the answer.
3. **No external references:** Self-contained without attachments or phrases like "see table above".
4. **Clear grammatical attachment:** Every clause attaches unambiguously to one referent.
5. **Question is specific:** Removing the answer leaves constraints that point to exactly one entity.
6. **Claims are factual:** Every factual claim in the question is true.
7. **Unique obvious answer:** After research, one answer clearly dominates.
8. **Answer is correct:** Factually correct and verifiable against primary sources.

### How do reviewers decide between "Send Back (Red)" and "Fix and Approve (Yellow)"?

* **Red (Send Back):** The task is substantively broken (e.g., prompt fails quality checks, wrong answer, missing model failure, broken GT logic).
* **Yellow (Fix & Approve):** The issue is fixable in review without changing task substance (e.g., typos, formatting, minor GT structural order, reordering sources, missing page location tags). Reviewers must not send tasks back for Yellow issues alone.

### When are reviewers allowed to reject/send back a task?

Reviewers should only reject a task when they assign it a Subjective Quality Score (SQS) of 1 or 2. Rejecting a task given an SQS score of 3 or above is considered a review error.

### What structure must every reviewer send-back comment follow?

When sending a task back, reviewers must include:

1. Praise for what was done well.
2. Name each error specifically with its correct error tag.
3. Concrete, in-depth guidance on how to fix the task.

### How should reviewers handle suspected AI/LLM usage?

If a task appears AI-generated (e.g., templated GT text, empty/deleted ChatGPT share links, fabricated citations), reviewers must **escalate** the task rather than simply sending it back. Escalation flags it for the project team and protects reviewer pay for the work performed.

