# Examples

## Good Examples

### 1. Ready-to-Deliver (RTD) Golden Examples

* **Example 1: The Earliest-Born Judge** (*Domain: Legal*)
* **Prompt**: *"I'm researching Indian judicial history through a case chain. In 1984, the Supreme Court of India upheld the Hindu Marriage Act, 1955 provision on restitution of conjugal rights, disagreeing with a 1983 ruling where a single judge of an Indian High Court had struck that provision down as unconstitutional. That overruled case was brought by a well-known South Indian film actress. Now, the current official website of that same High Court maintains a 'Former Judges' page listing former judges including judges of the common (undivided) High Court with a recorded date of birth for each. According to that page, which former judge listed there has the earliest recorded date of birth?"*
* **Correct Answer**: `A. [cite_start]Ranganadham Chetty` 


* **Model Trap**: The AI model traced the two-case legal chain correctly (*Saroj Rani v. Sudarshan Kumar Chadha* $\rightarrow$ *T. Sareetha v. T. Venkata Subbaiah* $\rightarrow$ Andhra Pradesh High Court). However, when scanning the long "Former Judges" roster on `aphc.gov.in`, it read only part of the page, named `A. Srinivasachari` (born 10 September 1901), and falsely asserted that nobody on the page was born earlier. In reality, Justice A. Ranganadham Chetty (born 23-02-1900) appears further down the same page.




* **Example 2: The 1999 NFL Draft Chain** (*Domain: Sports*)
* **Prompt**: *"In the 1999 NFL Draft transactions, a team both traded away exactly one pick to a team in its 2025 division and acquired exactly one pick from a team outside its 2025 division but inside its 2025 conference. In the final NFL season in which the first player that draft-transaction team selected in the 1999 NFL Draft signed with any NFL team, the draft-transaction team played a Week 6 game. The player who led the winning team in rushing yards in that game was born in a particular year. In the NFL Draft held in that birth year, among players with a nonzero listed career rushing-yards total, using standard competition ranking, which player ranked 7th-lowest?"*
* 
**Correct Answer**: `Calvin Sweeney` 


* **Model Trap**: The model successfully traced all preliminary hops (New York Jets $\rightarrow$ Randy Thomas $\rightarrow$ 2010 season Week 6 game vs. Broncos $\rightarrow$ LaDainian Tomlinson born June 23, 1979 $\rightarrow$ 1979 NFL Draft). However, when enumerating the final long draft statistics table under standard competition ranking (including negative rushing yard totals), it skipped three draftees (Rod Kush, Stan Rome, Frank Manumaleuga) and incorrectly answered `Gordon Jones`.


* **Example 3: The Statutes and the Celtics** (*Domain: History / Sports / Law*)
* **Prompt**: *"A Volume 2 installment of Statutes of California corresponds to the same two calendar years as the Boston Celtics regular season between 1950-51 and 1960-61, inclusive, in which the team had at least 50 wins, at least 20 losses, and an assists leader who averaged more than 8.0 assists per game. In that volume, the Assembly Concurrent Resolution numbered by the least common multiple of 5 and 7 concerns a specific person. According to that resolution, the person was a director of which organization?"*
* 
**Correct Answer**: `the San Diego Padres baseball club` 


* **Model Trap**: The model correctly resolved every multi-hop clue (1958–59 Boston Celtics season $\rightarrow$ Statutes of California 1959 Volume 2 $\rightarrow$ LCM(5,7) = 35 $\rightarrow$ Assembly Concurrent Resolution No. 35). However, because it could not cleanly extract the scanned page 5501 text from the PDF volume within tool time, it inferred the resolution's subject from external dental leadership records (`Dr. Clifford F. Loader` / `Pierre Fauchard Academy`) instead of reading the scanned resolution text, which was actually about `Edgar A. Luce`.


* **Example 4: The Student-Visa Table (SEVIS)** (*Domain: Government Data*)
* **Scenario**: A 6-hop chain across pop culture, sports history, celebrity deaths, and official government data (Glen Powell birthdate $\rightarrow$ Air Jordan release year 1984 $\rightarrow$ Packers vs. Seahawks game Oct 21, 1984 $\rightarrow$ Seahawks 2nd Super Bowl year 2026 $\rightarrow$ Ray Charles death month June $\rightarrow$ SEVIS lookup for June 2026 Belgium Bachelor's students).
* 
**Correct Answer**: `551` 


* 
**Model Trap**: The model correctly identified every clue leading to the June 2026 SEVIS table. However, when the target web page failed to render text via web browser snippets, it substituted the adjacent May 2026 figure (`570`) instead of opening the direct SEVIS data index table.





---

### 2. Real Prompting Techniques (Worked Examples)

* **Watch Exact Words**: In a 1915 baseball weekly report covering a league election on page 3, asking specifically for who *handed in* a club's ballot yielded `E.T. Briscoe`, whereas the AI grabbed `Jack Flannery` (the club president listed on a similar roster).
* **Who Did It to Whom**: In a 1946 Leonard Bernstein letter stating he was discussing someone *with* another person, asking who he was discussing him *with* yielded `Mrs. Wyman` (the AI grabbed the prominent names `Aaron Copland` and `Marc Blitzstein`).
* **The Summary That's Wrong**: On a composer's reference page where the intro summary states "five operas" but the full detailed list below lists 6 (including an unfinished one), counting 6 operas leads to the correct issue of an old magazine advertising for `A harpist` (the AI trusted the summary count of 5 and answered `piano player`).
* **The Odd Box That Says Something Strange**: In a US DOJ Google antitrust trial exhibit spreadsheet, asking what a specific worksheet was labeled yielded `Internal Google testing only` (the AI grabbed a neat version name `Model v0.5` from the wrong exhibit).
* **The Neighbour That Doesn't Match**: On a 1915 scanned newspaper page with the headline *"ITALY DECLARES WAR!"*, asking whose portrait appears directly above the headline yielded `Frank P. Sadler` (a local man in the caption) rather than `Thomas R. Marshall` (a national politician guessed by the AI based on the headline subject).
* **The Wrong Date Sitting Right There**: In a boundary marker survey datasheet listing set dates and check dates side-by-side, asking for the exact set date yielded `June 24, 2007` (the AI grabbed `September 4, 2013` from the same record).
* **The List That Leaves Your Answer Out**: In the 1839 US House Speaker election, asking for whom a candidate voted in the 8th round specifically yielded `George C. Dromgoole` from the official House Journal (an online voting summary database lined up rounds incorrectly and led the AI to answer `Cave Johnson`).
* **Scanned Table Read in Wrong Order**: In a 1915 Alabama coal-mines report where the OCR text layer read down columns instead of across rows, reading the scanned visual image row across yielded `274` (the AI reading the hidden OCR layer answered `172`).
* **The "Same as Above" Mark**: In an 1899 USGS dictionary of altitudes, asking for the elevation at the L&N Railroad crossing in Anniston yielded `665 feet` via a ditto mark (`Do.`) copying the row above (the AI keyword search missed the ditto mark and grabbed `694 feet` from a different entry).
* **Number Used as a Position**: Using an American footballer's career rushing yards as an index position $N$ down an official state list of governors yielded `Harrison Reed` (the AI treated the number as a value or counted in the wrong state's list, answering `George W. P. Hunt`).
* **Three Clues Pointing to One Box**: Intersecting page number (Michael Jordan's jersey 23) and rank in a table (26th) in an NCAA record book yielded `Paul Atkinson Jr.` (the AI got tangled computing page and rank).
* **Add Up Years to Find the Right Report**: In annual state banking reports for a bank paying back shareholders, calculating running totals across years to identify the final payment report yielded `January 5, 1920` (the AI guessed a year and opened the wrong report).
* **Not the Biggest or Smallest — The Odd One**: In a 1947–48 Idaho library report table showing "Donations Of Books" for five libraries (`28, 28, 320, 28, 28`), asking for the single non-matching outlier value yielded `320` (the AI skimmed and answered `28`).
* **Two Different Things, Same Name**: A soil type in a Georgia farming table sharing its name (`Congaree`) with a Native American tribe, South Carolina river, and national park yielded a crop yield of `4.0` (the AI stumbled on the name bridge and answered `8.0`).
* **Find It by Occurrence Count**: Asking for a researcher whose full name appears exactly 8 times in a single journal issue yielded `David Winslow Latham` (the AI skipped tallying mentions and grabbed a more prominent name).
* **The One That's Missing**: In a church statement representing six senior bishops signed by five, asking for the sole non-signer yielded the missing bishop's name (the AI assumed all six signed and named a signer).
* **The Same Thing with Another Name**: In a medical taxonomy chain asking for a condition containing a 9-letter word in a specific category, identifying the 9-letter word "cutaneous" yielded `Cutaneous somatic symptom disorder` (the AI grabbed `Tourette's disorder`).
* **Looks Like Maths, But the Answer is Printed**: Framing a Chicago Construction Code building area prompt to look like an arithmetic calculation when the final total is printed directly in a codebook table yielded `12,000 square feet` (the AI attempted math and got tangled).

---

### 3. Concise Good Prompts (Illustrating Quality Rules)

* 
**Rule 1 (Requires Search)**: *"Which 5th-century Welsh saint instructed the teacher of Samson of Dol, after reclaiming a stolen cow from a king whose brother was the patron saint of Devon?"* 


* **Rule 4 (Clear Grammatical Attachment)**: *"Who became head coach of the New Orleans Pelicans, succeeding a coach who had earlier served as associate head coach under Mike Krzyzewski at Duke?"*
* 
**Rule 5 (Question is Specific)**: *"Who founded the Polish-language Catholic radio station, launched in the early 1990s, that received early financing from an Uruguay-based billionaire of Polish descent?"* 


* **Rule 6 (Claims are Factual)**: *"Which wartime propaganda broadcaster was nicknamed 'Tokyo Rose' by Allied troops in the Pacific theatre?"*

---

## Bad Examples

### 1. The 5 Rejected Examples

* **Rejected Example 1: The Blog That Debunked Itself** (*Domain: Music*)
* **Prompt**: *"Tell me the name of a Raga in the Hindustani Classical Music which is similar or equivalent to the locrian mode of the western music theory? The notes used in both should be the same in order for them to be a match..."*
* 
**Claimed Answer**: `Raga Todi` 


* **Rejection Reasons (SQS 1/5)**: Factual error—Raga Todi contains *Pa* and *shuddha Ni*, whereas the Locrian mode has neither, so no canonical Hindustani raga matches Locrian notes. Built on an informal blog (`shambhavidas.blogspot.com`) that admitted the mapping was only "almost" and was debunked in its own comment section. None of the cited sources verified the answer, and the AI model actually gave the correct answer ("no such raga exists"), meaning there was no genuine model failure.




* **Rejected Example 2: Boilerplate Instead of Research** (*Domain: Celebrities / Public Figures*)
* **Prompt**: *"Which museum currently holds the original painting created by the artist who completed the ceiling fresco The Apotheosis of Saint Ignatius in the Church of Sant'Ignazio in Rome..."*
* **Claimed Answer**: Copy-pasted explanation acknowledging prompt invalidity rather than an answer.
* 
**Rejection Reasons (SQS 1/5)**: Domain mismatch—assigned under *Celebrities/Public Figures*, but content was 17th-century classical art history. Failed timelessness due to unanchored phrase "currently holds". Golden Trajectory and source fields contained generic platform review guideline templates (e.g., *"1. Read the prompt carefully..."*) with zero URLs or actual research steps.




* **Rejected Example 3: The Stump That Wasn't** (*Domain: Politics*)
* **Prompt**: *"During the exact calendar year of the 20th century when the United Kingdom held two separate general elections, a specific European nation's legislature passed a landmark constitution... Decades later, a politician who had previously worked as a professional classical concert pianist was elected as the Prime Minister..."*
* 
**Claimed Answer**: `1992` 


* 
**Rejection Reasons (SQS 1/5)**: Broken premise—UK two-election year (1974) did not match Lithuania's 1992 constitution, and former pianist Vytautas Landsbergis was Chairman of the Supreme Council / Head of State, never Prime Minister. The model correctly identified the factual inconsistency and refused to give an answer, which is a correct refusal rather than a model failure. GT contradicted itself by querying 1972, claiming 1992, and linking to a list of Greek Prime Ministers.




* **Rejected Example 4: The LLM Told on Itself** (*Domain: Celebrities / Public Figures*)
* **Prompt**: *"Which museum permanently houses the original painting created by the artist who designed the stained-glass windows for Grossmünster in Zürich..."*
* 
**Claimed Answer**: *"The prompt does not have a single verifiable answer due to ambiguous premises."* 


* **Rejection Reasons (SQS 1/5)**: High LLM usage detected—the contributor pasted raw LLM meta-commentary into answer, GT, source, and failure justification fields, including the LLM's own advice: *"you should not submit this prompt at all"*. Prompt was ambiguous and failed timelessness. Model did not fail.




* **Rejected Example 5: A Template with the Hard Part Missing** (*Domain: Art*)
* **Prompt**: *"Between January 2023 and December 2024, one Fortune 500 company completed the acquisition of another publicly announced business and disclosed the final purchase price in multiple official documents..."*
* 
**Claimed Answer**: Restated the final question (*"Using Cisco's official press release..."*) instead of providing an answer.


* 
**Rejection Reasons (SQS 1/5)**: Domain mismatch (assigned *Art*, content was *Business*). Underspecified and ambiguous prompt (did not specify which Fortune 500 company or acquisition; Cisco, ExxonMobil, and Broadcom all fit). Not complex enough (simple repeated lookup). Golden Trajectory contained unreplaced LLM placeholders like `[Acquiring Company]` and `[Target Company]`, and sources contained zero URLs.





---

### 2. Flawed Prompts (Illustrating Quality Rule Violations)

* **Rule 1 Violation (Common Knowledge / Single Lookup)**:
* 
*"What is the capital of France?"* (Common knowledge; no web search required).


* 
*"Who was Samson of Dol's teacher?"* (Single lookup; lacks multi-hop constraint chaining).




* **Rule 4 Violation (Ambiguous Grammatical Attachment)**:
* 
*"Who became head coach of the New Orleans basketball team succeeding the coach who served as associate head coach under Mike Krzyzewski?"* (Trailing modifiers and missing team/time specifics create ambiguous referents).




* **Rule 5 Violation (Under-Constrained / Not Specific)**:
* 
*"Who founded a radio station financed by an Uruguay-based billionaire?"* (Missing specific language/time constraints leaves multiple entities plausible).




* **Rule 6 Violation (False Premise)**:
* *"In what year did the TV show 'Tokyo Rose' first air?"* (False premise—'Tokyo Rose' was a radio propaganda broadcaster, never a TV show).



---

## Best Practices

### 1. Prompt Writing Best Practices

* **Word Count & Style**: Write clear, self-contained English prompts between **70 and 150 words** in a natural search style.
* 
**Multi-Hop Chaining**: Require at least **3 distinct primary sources** across the web, chaining facts so that removing the answer leaves constraints pointing to exactly one entity.


* 
**Timelessness**: Lock any mutable fact (superlatives, "current" officeholders, prices, counts, live datasets) to a fixed date, year, or dated snapshot.


* 
**Direct Questions**: Pose a direct question; never write process instructions that narrate lookup steps or name exact sources/pages to open.


* **Niche Domain Depth**: Lean into niche, well-documented corners of assigned domains rather than famous or common facts.

### 2. Answer Formatting Best Practices

* **Single Entity**: Provide exactly one correct answer as a short string representing a specific entity (Name, Place, Date, Number, Title, Event).
* **Highlightable Text**: The final answer must be printed directly on a primary web page where it can be highlighted in plain text.
* **No Mental Math**: Never compute, calculate, or derive the final answer in your head—any final numeric value must be read straight off the source page.

### 3. Golden Trajectory (GT) Best Practices

* **Required 4-Part Structure**: Format every step strictly as:
1. 
`Step X: Search: "<exact query>" and <navigation path>` 


2. `Step Y: Fetch: <URL> to find <answer> (at specific location on page)`
3. 
`Step Z: Verify: confirms <specific constraint from prompt>` 


4. 
`Step W: Filter: explains how step narrows field of possible final answers` 




* 
**Forward Derivation**: Always derive the trajectory forward from the prompt's clues—never reverse-engineer it backward from the answer.


* **Defensibility Test**: Read the trajectory back as a stranger to confirm no alternative answer could reasonably be reached.
* 
**No LLM Templates**: Write all steps in your own words; never use LLM generators or generic boilerplate.



### 4. Source Selection Best Practices

* 
**Primary Evidence**: Rely on primary or authoritative sources (official government records, gazettes, legal databases, peer-reviewed work).


* 
**Quality over Quantity**: Three direct, authoritative primary sources beat ten informal blog posts.


* 
**Direct Deep Links**: Provide direct, functional deep-link URLs to exact pages rather than homepages or search result pages.


* **Incognito Tab Verification**: Ensure every source URL is live, non-paywalled, accessible globally, and openable in an incognito browser tab.

### 5. Reviewer Best Practices

* **Default to Edit & Approve (Yellow)**: For sound prompts and correct answers with SQS $\ge 3$, reviewers must correct fixable cosmetic issues (typos, formatting, minor GT/source cleanup) themselves and approve.
* **Send Back (Red) SQS Rule**: Reject tasks (send back) **only when assigning an SQS score of 1 or 2** for substantive broken errors (false premises, wrong answers, unusable GT, domain mismatch).
* **Feedback Structure**: Always structure send-back comments in three parts:
1. 
*Praise*: What was done well.


2. 
*What's wrong*: Specifically named and correctly tagged errors.


3. 
*How to fix it*: Concrete, actionable guidance.


* 
**Escalate LLM Usage**: If AI generation or boilerplate is suspected, escalate directly to project administrators rather than sending the task back.
