# English inventory

**Governs EN-matrix spans only.** Layer 0 decides what is an EN-matrix span. An English word standing inside a ZH-matrix sentence is terminology and is never a candidate here — `deploy 完就 rollback` contains no English span.

Source aliases used for confidence marks, file-local: **L** = professional-editor edit study, **P** = excess-vocabulary corpus study, **R** = detection study Table 12, **S** = slop taxonomy, **F** = fiction/RP community ban lists. All five come from the sepia parent's research ledger. Confidence tags: `[grounded]` = follows from a measured claim in a parent skill (alias given), `[inference]` = operational extension the parents support but did not measure, `[speculative]` = judgment call.

## 0 Counting and tier mechanics

**Counting convention.** English is counted in **words**. A multi-word banned phrase is **one hit**. A hyphenated compound is one word. Code identifiers, file paths, CLI flags, and version numbers each count as **one unit** toward word totals and are never themselves candidates.

| Tier | Trigger | Default action |
|---|---|---|
| **1** | one hit | Replace (or delete, where marked) |
| **2** | cluster inside one paragraph: paragraph <100 words → **2+ hits**; paragraph ≥100 words → **3+ hits** | Rewrite the cluster; keep at most one member |
| **3** | whole-text density of the **same word**: text <200 words → **3+**; 200–1000 → **5+**; >1000 → **>0.5% of total words** | Vary or cut down to threshold |

Tier 2 and Tier 3 thresholds are inherited operational stipulations, not measurements `[inference]`. The cumulative principle underneath them is measured: a single hit is not a verdict, slop is cumulative `[grounded: S]`.

**Edit mix.** Across a whole pass, EN edits should skew **replace ~74% / delete ~18% / insert ~8%** `[grounded: L]`. When torn, cut. The only insert that may grow the text is real specificity taken from the text or from the user.

**Tier action vs. edit scope.** Replacement is legal at every scope. A tier entry whose default action is *delete the sentence* is legal only at structural scope; at bounded scope it goes to the user-confirmed deletion list; at in-place scope it is reported, never executed. Intra-sentence deletion (a wrapper noun, a stance adverb) stays legal at bounded scope.

**Force level mapping** `[inference]`: minimal = Tier 1 only; standard = Tier 1 + Tier 2; aggressive = Tier 1 + 2 + 3 + syntax templates. Every EN fix here is a style move and counts against the calibration budget.

**The list is examples, not a boundary.** What is banned is the *rhetorical action* — significance inflation, sycophantic opening, copula avoidance, empty hedging — not the literal string. Swapping in an unlisted synonym that performs the same action is still a hit. The converse holds: a listed word doing real work in its literal sense is not a hit. Judge the action.

---

## 1 Tier 1 — replace on a single hit

### 1.1 Throat-clearing openers
Delete the opener; start at the claim.

Here's the thing · The uncomfortable truth is · Can we talk about · Let's be honest · I'll be frank · It's worth noting that · It's important to note (that) · At its core · At the end of the day · In today's world · In a world where/of · What this means is

Retention: none in professional prose. In fiction dialogue a character may say any of these `[grounded: sepia whitelist — quoted material keeps its texture]`.

### 1.2 Emphasis crutches
Delete. The emphasis has to come from the claim.

Full stop. · Let that sink in. · Make no mistake. · Mark my words. · Read that again. · Period. · I promise.

### 1.3 Sycophantic and meta
Delete. In a reply, answer the question with the first sentence.

Great question! · You're absolutely right! · Certainly! · Of course! · I hope this helps! · Let me know if you'd like me to expand · In this essay we will explore · As we'll see · Here is a/an…

### 1.4 Filler phrases

| Cut | Use |
|---|---|
| In order to | To |
| Due to the fact that | Because |
| At this point in time | Now |
| It is important to note that | *(delete)* |
| It goes without saying | *(delete)* |
| X has the ability to | X can |
| a wide range of / a variety of | the actual number, or *(delete)* |

### 1.5 Copula avoidance
The AI-sense of these is always the same move: dodging *is/are/has*.

serves as a · stands as a · represents a · functions as a → **is a**
boasts a · features a · presents a → **has a**

Retention: *represents* in its literal sense (a symbol represents a value; a delegate represents a district).

### 1.6 Phrasal significance inflation
Fixed formulas that are inflation every time they appear. Single adjectives of significance are *not* here — they go to Tier 2, because an adjective can be true.

a testament to · serves as a testament to → **shows**
showcases · underscores · highlights (in the sense "shows that X matters") → **shows**
paving the way for → **led to**, or name what happened next
watershed moment → turning point · indelible mark → lasting effect · paradigm shift → major change
groundbreaking · cutting-edge → **new**, or the actual capability
cautionary tale → say what went wrong
amidst → amid, among, or **during**

`[grounded: R formula phrases, L signature phrases]`

### 1.7 Inflated verbs

utilize → use · commence → start · endeavor → try · ascertain → find out · facilitate → help · cultivate → build, grow · elucidate → explain · ameliorate → improve · galvanize → motivate · bolster → support · spearhead → lead · catalyze → trigger · reimagine → rethink

### 1.8 Business jargon

leverage → use · navigate → handle, deal with · unpack → explain · lean into → accept, try · deep dive → detailed look · game-changer → important change · circle back → revisit · synergy → cooperation · ecosystem → system, community · streamline → simplify · empower → let, enable · actionable → practical · learnings → lessons · thought leader → expert · best practices → good practices · holistic → complete, whole

**Literal carve-out.** Keep the word when the domain sense is the one meant: *navigate* in graph, routing, UI, or pathfinding contexts (`the router navigates the topology with Dijkstra`); *ecosystem* for an actual biological system; *streamline* in fluid dynamics; *leverage* in finance and mechanics.

**Parent conflict resolved:** sepia files *navigate*, *foster*, *harness* together as performance verbs judged by clustering. *Navigate* is promoted to Tier 1 here because it has a one-word plain replacement and an explicit, testable literal carve-out; *foster* and *harness* stay Tier 2 `[speculative]`.

### 1.9 Signature phrases (prose and fiction)
Delete, or replace with the concrete thing.

hung in the air · the air was thick (with) · in the pit of her/my stomach · a constant reminder of · the weight of [abstraction] · unspoken

`[grounded: L]` — these were among the phrases professional editors removed most often.

### 1.10 Stance adverbs
Delete. They intensify a claim instead of supporting it.

fundamentally · essentially · ultimately · arguably · undeniably · importantly · notably · interestingly · significantly · remarkably · incredibly · truly · deeply

**Reread check:** delete the adverb and reread the sentence. If the meaning is unchanged, the deletion is correct — that is the whole test.

**Parent conflict resolved — *just, really, actually, honestly, genuinely, literally*.** The shuorenhua parent bans them as -ly/filler; the sepia parent restores them as suppressed human discourse particles `[grounded: P]`. Discriminator `[inference]`: in a **voiced** sentence — dialogue, first person, a reply to a person — they are register and are kept or restored (§4). In **expository** prose (reference docs, API descriptions, release notes) they are filler and are deleted. `it's just a cache` in a forum reply stays; `the API just returns the cached value` loses *just*.

---

## 2 Tier 2 — flag when clustered in a paragraph

Individually defensible; the paragraph is the unit of judgment. Keep at most one member per paragraph and rewrite the rest.

| Class | Members |
|---|---|
| Abstract-grandeur nouns `[grounded: R, P]` | tapestry, testament, symphony, kaleidoscope, landscape *(figurative)*, realm, journey *(figurative)*, beacon, camaraderie, solace, resilience, nuance, myriad, plethora, cornerstone |
| Performance verbs `[grounded: R, P]` | delve, foster, harness, resonate, elevate, embrace, transcend, unravel, ignite, grapple, weave/weaving, unleash, revolutionize, underpin, encompass |
| Inflation adjectives `[grounded: P, R]` | intricate, vibrant, palpable, profound, pivotal, crucial, transformative, multifaceted, fleeting, bustling, nuanced, paramount, poised, burgeoning, nascent, quintessential, overarching |

Notes:
- *delve* stays Tier 2 by explicit parent instruction: one hit means nothing `[grounded: sepia whitelist]`. Two in a paragraph is a hit.
- *underscore* sits in Tier 1 §1.6 rather than here — its figurative use has no other sense, so it needs no cluster to convict `[speculative]`.
- *landscape*, *journey*, *realm* are exempt when literal: terrain, an actual trip, a mathematical realm.
- *crucial*, *pivotal*, *paramount* are exempt when the text goes on to say **why** — a stated stake is the retention condition `[inference]`.

---

## 3 Tier 3 — flag on whole-text density only

Ordinary words. Only repetition convicts. Apply the §0 density thresholds to each word separately.

significant · innovative · effective · dynamic · scalable · compelling · unprecedented · exceptional · remarkable · sophisticated · instrumental · comprehensive · robust · seamless · powerful · key *(as adjective)*

*robust* and *seamless* are demoted from sepia's inflation-adjective class to Tier 3 because both are load-bearing technical terms — robust error handling, seamless failover — and a single occurrence in engineering prose is normal `[speculative]`.

---

## 4 Syntax templates to hunt

Part-of-speech shapes, not words; the lexicon tiers do not catch these. Each is 2–5× overrepresented in model prose and heavily edited out by professionals `[grounded: L, P]`. Treat a template hit like a Tier 1 hit inside its sentence.

| Template | Signal | Default action | Rewrite |
|---|---|---|---|
| a/the [abstract noun] of [noun] (and [noun]) | *a mix of pride and fear*, *a sense of wonder*, *the weight of expectation* | Cut the wrapper noun or name the concrete thing | "She felt a sense of relief." → "She stopped bracing." |
| the [adj] [noun] of [possessive] | *the intricate tapestry of its dependencies* | Rewrite from scratch | → "Forty packages. Six pinned to versions nobody recognizes." |
| Trailing participial clause | *"…, cutting our CI time in half"* — up to 5× human rate | Break out into a finite-verb sentence | "The build finished in nine minutes, cutting CI time in half." → "The build finished in nine minutes. That halved CI time." |
| Leading participial clause | *"Stuffing his mouth, Joe ran."* | Same | → "Joe stuffed his mouth and ran." |
| Nominalization as subject | *realization, determination, transformation* heading a sentence — 2× human rate | Turn the noun back into a verb | "The realization that the cache was stale came late." → "We realized late that the cache was stale." |
| Paired abstractions "X and Y" | *desperation and resolve*, *curiosity and caution* | Keep one | → "She was curious." |
| not only X but also Y · it's not X, it's Y | — | Say the one thing you mean | "It's not a bug, it's a design flaw." → "It's a design flaw." |
| Rule of three | three parallel adjectives, clauses, or images, repeatedly | Two or four; break the rhythm | "fast, reliable, and maintainable" → "fast and maintainable" |

**Retention condition for all eight:** a template used **once** in a long text is style, not slop. Convict on repetition inside the same section, or on a template hit stacked with lexicon hits in the same paragraph `[inference]`.

**Reread check:** read every rewritten sentence aloud. Grammatical but unsayable is its own slop dimension `[grounded: S]`. If no native speaker would say it or write it in a letter, redo it in speech-shaped syntax.

---

## 5 Fiction-only inventory

**Applies only when scene = fiction.** Do not run §5 against docs, README files, release notes, tickets, or forum replies — *felt*, *seemed*, and *noticed* are ordinary hedges in professional prose, and flagging them there is an over-correction.

### 5.1 Fiction slop — Tier 2, cluster-judged `[grounded: F]`
ozone · petrichor · shimmering · thrums · gossamer · "barely above a whisper" · "eyes gleam/glint/alight" · "despite herself" · "breath catches" · "heart skips" · "shivers down the spine" · "voice like [material]"

Two in a scene is a hit. Replace with a detail specific to *this* character in *this* room; never with a blander paraphrase — the blander paraphrase is the documented machine failure `[grounded: L]`.

### 5.2 Filter words — Tier 1 within fiction `[grounded: F]`
felt · seemed · realized · noticed · knew · watched as · saw that

Delete the filter and render the thing directly. "She felt the floor shake." → "The floor shook."
Retention: keep the filter when the POV character's *uncertainty* is the point ("It seemed empty. It wasn't.").

### 5.3 Speech tags — Tier 3, density-judged
Rotating *notes, observes, remarks, muses, offers, quips* is machine elegance. *said* on repeat is human `[grounded: P]`. Convict on density of non-*said* tags, not on any single tag.

### 5.4 The professional-prose counterpart
Outside fiction, the same underlying artifact appears as **"seem to + verb"**. Replace with the verb itself unless the uncertainty is real: "The service seems to time out." → "The service times out." `[grounded: L, artifact #1]`

---

## 6 What to add back — the underused human register

Instruct-tuned models systematically suppress these; measured usage runs at 13–80% of the human rate `[grounded: P]`. This is a **positive target**, not a quota. Restore only to the degree the scene, the genre, and the author's voice allow — sprinkled, not poured.

These are rewrites of existing content, not insertions of fact: restoring a contraction or a *because* adds no claim, changes no responsible party, and is legal under the truth-preserving contract at any scope that permits editing.

| Restore | Examples | Where it fits |
|---|---|---|
| Contractions | don't, it's, wouldn't | Anything but the most formal reference prose |
| Discourse particles | well, anyway, just, really, actually | Voiced prose only — see §1.10 discriminator |
| Plain causal connectives | because, so | Everywhere. *because* is measured at ~20% of the human rate in one model `[grounded: P]`; prefer it over *as such*, *thereby*, *thus* |
| Hedges and emphatics | almost, sort of, for sure, obviously | Where the uncertainty or the certainty is real |
| Synthetic negation | "no answer was good enough" — runs at about half the human rate | Anywhere; it is the cheapest single register fix `[grounded: P]` |
| Pro-verb *do* | "and she did", "it does" | Avoids repeating the full predicate |
| Plain speech tags | said, says | Fiction and quoted speech |
| First/second person, direct questions | "you'll want to pin this" | Where POV and genre permit |
| Blunt language | — | Only where the register genuinely calls for it |

**Reread check:** count contractions and *because* in the finished EN spans. Zero of either, in text that is not formal reference prose, means the register fix did not happen.

---

## 7 False-positive whitelist

Over-correction is its own fingerprint. Do **not** flag or "fix" these `[grounded: sepia §7]`:

| Not evidence of AI | Why |
|---|---|
| Correct grammar and clean punctuation | Humans write cleanly; injecting imperfection is itself a detectable gimmick |
| A single em-dash, semicolon, or *delve* | One hit means nothing; only clusters count |
| Neutral or formal tone in a formal genre | Register match beats forced casualness |
| A banned word inside quoted dialogue, a quoted error message, or an in-world document | Quoted material keeps its texture |
| A banned word in a proper noun, product name, or API identifier | `Elevate SDK`, `foster_child_id` are names, not diction |
| The author's own verified habits | If the user's samples use em-dashes or *moreover*, those stay |
| Ordinary, moderate sentences | Slack is human; do not polish every line to distinctiveness |
| Literal domain senses | See the §1.8 carve-out list |

> Informality is not a disguise. In the tested humanization conditions of R, expert readers still detected other machine-patterned cues; casual language alone did not remove them. That result does not establish that every informal model output is detectable.
