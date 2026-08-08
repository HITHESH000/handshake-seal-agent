# Answer Requirements

## Accuracy

* Provide exactly one correct answer formatted as a single short entity (such as a Name, Place, Date, Number, Title, or Event).
* The answer must be factually correct and hold up against primary sources.
* All constraints in the prompt combined must lock on to exactly one unique entity, proving no other plausible candidate satisfies every condition.
* The answer must be verified as accurate before building the rest of the task, as a wrong reference answer invalidates the answer, the golden trajectory, and all model-failure sections simultaneously.
* Every figure, number, and URL cited across all task blocks must match the answer exactly.

## Sources

* The answer must be verified by tracing it backward through primary and authoritative sources on the web (e.g., official records, peer-reviewed work, original documents).
* The final source used to confirm the answer must be an authoritative primary source openable in an incognito tab, with no contradicting information present in another comparable source.
* The source list must map directly to the steps in the golden trajectory, featuring at least three genuinely necessary deep-link sources from different domains.

## Verification

* Contributor self-verification is required: you must be able to verify the answer yourself by tracing it backward through web sources before task submission.
* The golden trajectory must culminate in a final primary-source check step to confirm the answer.
* The answer must be verified against live, direct deep-link URLs (not homepages or search result pages).

## Formatting

* Must be formatted as a short string representing a single entity (Name, Place, Date, Number, Title, or Event).
* Long-form, descriptive, or explanatory paragraph answers are strictly prohibited.
* Standardized formatting must be maintained (e.g., plain entity presentation, clear date formatting).

## Common Mistakes

* **Explanatory Paragraphs:** Providing long-form explanations or multi-sentence descriptions instead of a single short entity.
* **Mismatched Data:** Discrepancies in numbers, figures, or details between the reference answer, golden trajectory steps, and source list.
* **Unverifiable/Outdated Answers:** Submitting answers that rely on mutable facts without locking them to a specific date/snapshot, or answers contradicted by primary sources.
* **Multiple Defensible Answers:** Crafting prompts where multiple alternative entities could plausibly answer the question.
* **False Premises:** Deriving an answer based on a prompt that contains a wrong statement or misidentified entity.

