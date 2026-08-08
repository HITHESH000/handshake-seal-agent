# Examples

## Good Examples

* **Prompt Example:** "Which 19th-century botanist, born in a town now part of modern-day Slovakia, named a genus of orchids after the wife of a colleague who later became director of Kew Gardens?"
* **Failure Explanation Example:** "The model identified the correct radio station but then attributed its founding to the wrong person—confusing the station's financier with its founder. Each fact was retrievable, but the model didn't keep the financier and founder roles distinct across sources."
* **Valid Answer Types & Examples:**

  * **Name:** Marie Curie
  * **Place:** Reykjavík
  * **Date:** 14 July 1789
  * **Number:** 42
  * **Title:** The Tin Drum
  * **Event:** Treaty of Utrecht
* **Sign-Off Request Format (Reviewers):** `@[signer] | Task ID: [xxxx] | Review #[X] | SQS Score [X] | About to Approve / Send Back [one-sentence reason].`

## Worked Example (Golden Trajectory & Prompt)

* **Prompt:** "A Volume 2 installment of Statutes of California corresponds to the same two calendar years as the Boston Celtics regular season between 1950-51 and 1960-61, inclusive, in which the team had at least 50 wins, at least 20 losses, and an assists leader who averaged more than 8.0 assists per game. In that volume, the Assembly Concurrent Resolution numbered by the least common multiple of 5 and 7 concerns a specific person. According to that resolution, the person was a director of which organization?"

* **Trajectory Steps:**

  * *Step 1:* Search: `'Boston Celtics regular season records'` and clicked top result to `https://www.basketball-reference.com/teams/BOS/`, scanned table, clicked `"1958-59"` to open `https://www.basketball-reference.com/teams/BOS/1959.html`.
  * *Step 2:* Fetch: `https://www.basketball-reference.com/teams/BOS/1959.html` to find 1958-59 stats (Bob Cousy >8.0 APG in "Team Leaders").
  * *Step 3:* Verify: Confirms Celtics season constraint (≥50 wins, ≥20 losses, assists leader >8.0 APG).
  * *Step 4:* Filter: Locks "two calendar years" to 1958 and 1959.
  * *Step 5:* Search: `'least common multiple of 5 and 7'` → `https://byjus.com/maths/lcm-of-5-and-7/`.
  * *Step 6:* Fetch: `https://byjus.com/maths/lcm-of-5-and-7/` to find LCM(5, 7) = 35.
  * *Step 7:* Verify: Confirms resolution number constraint (No. 35).
  * *Step 11:* Verify: Confirms "director of which organization?" constraint for ACR No. 35 in the 1958–1959 Volume 2 installment.
  * *Step 12:* Filter: Identifies person (Edgar A. Luce) and the single organization he was director of.

## Bad Examples

* **Common Knowledge Prompt:** "What is the capital of France?" (Flagged as common knowledge, single lookup, no search needed).
* **Poor Failure Explanation:** "The model got it wrong because it's bad at this kind of prompt." (Flagged for no specifics and no diagnostic value).
* **Invalid Answer Paragraph:** "Several scientists contributed, but the most influential was..." (Flagged as a paragraph instead of picking one entity plainly).
* **Invalid Model Failures (Do Not Count):**

  * Formatting or rounding differences (e.g., "1789" vs "14 July 1789").
  * Abbreviations or stylistic variations in the answer.
  * Model reaches right answer via sloppy reasoning.
  * Failures caused by an unclear prompt rather than model limitation.
  * "Response Failure Justification: N/A" or correct model refusal.

## Best Practices

* **Lean Into Domain Depth:** Target niche, well-documented corners of a domain rather than famous facts (e.g., a specific border treaty footnote is much better than asking for the capital of France).
* **Chain Multiple Facts:** Design questions by chaining constraints so a strong AI model with search gets it wrong, but a careful human researcher following your steps can solve it.
* **Anchor on Rare Constraints:** Search the rarest fact in the question first to narrow the candidate set as fast as possible.
* **Quote Distinctive Phrases:** Quote distinctive phrases verbatim during searches to surface authoritative pages quickly.
* **Open Authoritative Results:** Prefer official sites, encyclopedias, and primary documents over aggregators.
* **Verify Against Primary Sources:** Ensure the final step of a Golden Trajectory is always a primary-source check rather than a Wikipedia confirmation.
* **Defensibility Test:** Read Golden Trajectories back as an outsider to verify whether anyone following the steps could reasonably land on a different answer; if so, tighten the open step.
* **Quality Over Quantity in Sources:** Three solid primary sources are better than ten blog posts.
* **Write in Your Own Words:** Never use an LLM or AI tools to write Golden Trajectories or generate context.
* **Constructive Reviewer Feedback:** Every send-back comment must be structured as:

  1. Praise what was done well.
  2. Name and tag each error specifically.
  3. Provide concrete, in-depth fix guidance.

