# Pass 2 — Discourse flow

> This file is explanation, examples, and operating detail. The single source of the behavioural contract is `SKILL.md`; where the two differ, `SKILL.md` governs.
> 本檔案是解釋、示例與操作細則；行為合同的單源是 `SKILL.md`，兩處表述不一致時以 `SKILL.md` 為準。

> ## SCOPE — the numbers here are English-measured ／ 適用範圍：本檔數字皆為英文語料實測
>
> ### EN
>
> - **The percentages and scores in §1, §4 and §5 are English-corpus measurements.** On a ZH-matrix span they are not quoted, not converted, not approximated, and never reported — no "~19%", no "0.2–0.3%", no "63–70%", no "2.33 vs 2.12", and no human/AI columns. Neither parent skill carries a Chinese measurement baseline, so a Chinese figure has nothing to be checked against. *(grounded: every source cited in this file measured English text, and the absence of a Chinese baseline is a fact about these two skills — not an estimate.)*
> - **§5 (Names) does not run on Chinese text at all.** Elara / Ava / Amelia / Emily / Sarah is a distribution over English given names; it says nothing about a Chinese cast list, and a Chinese name that happens to recur is not evidence of anything. The §5 **fix** — name from the story's specific world, let surnames and nicknames do the social work — is ordinary craft advice and stays available; the name list and its percentage do not. *(inference)*
> - **The qualitative moves are language-neutral and do apply.** The outline test (§1), the QUD check read as a set of move *types* rather than as frequencies (§1), the middle-third check (§2), and the position tells (§3) describe shapes on the page, not measured quantities. They run on ZH-matrix spans as written. *(inference)*
> - **No aggregate verdict on Chinese text.** A finding on a Chinese span names the shape you can point at in the draft, in the Chinese inventories' terms. It never closes with a score, a rate, or an overall human-vs-machine call. *(inference)*
>
> **Reread check (any review with a ZH-matrix span):** search your own report for a number that came from this file. If one is attached to Chinese text, delete it and restate the point as the shape you actually saw — or drop the point.
>
> ### 中文
>
> - **§1、§4、§5 的百分比與量表分數都測在英文語料上。** 中文母語段落一律不引用、不換算、不取近似、不寫進報告——不出現「約 19%」「0.2–0.3%」「63–70%」「2.33 對 2.12」，也不列人類／AI 兩欄。兩個母技能都沒有中文語料基準，中文的數字無從查核。（grounded）
> - **§5（命名）完全不跑中文。** Elara／Ava／Amelia／Emily／Sarah 是英文名字的分布，對中文人物表沒有任何說明力；中文裡某個名字剛好重複出現，也不構成證據。§5 的**處方**——依故事世界取名、讓姓氏與小名承擔社會關係——是一般寫作建議，照用；那份名單與那個百分比不用。（inference）
> - **質性動作跨語言成立，照跑。** 大綱測試（§1）、把 QUD 當成一組提問類型而非頻率來檢查（§1）、中段檢查（§2）、位置訊號（§3），描述的都是文字在頁面上的形狀，不是量測值，中文母語段落照原文執行。（inference）
> - **不對中文文本下總體判定。** 中文段落的發現只講你能在草稿裡指出來的形狀，用中文清單的說法寫；不以分數、比率或整體的人／機判斷收尾。（inference）
>
> **回讀檢查（凡是含中文母語段落的審閱）：** 在自己的報告裡搜尋本檔來的數字。只要有一個掛在中文文本上，就刪掉，改寫成你實際看到的形狀；寫不出來就整條不要。

The layer between plot and sentences: how paragraphs advance, where the energy sags, and where things sit on the page. Evidence: QUDsim/COLM 2025 (Q), Tripto et al. EMNLP 2025 (T), Russell et al. ACL 2025 (R), Beguš 2024 (B), asavvin's outline test (A). Stable source identities live in the repository research ledger; single-letter aliases in this file are file-local. Prescriptions are Sepia design inferences unless a cited source explicitly tested the intervention.

## 1 The QUD check — what question does each paragraph answer?

Every paragraph implicitly answers a question. In QUDsim's tested samples, two models given the same premise independently reused the sequence *scene briefing → justifying the deception → social consequences → the weight of responsibility* (Q). Surface rewording does not change that question sequence; changing it requires reordering or replacing the underlying moves.

**Check:** List one implicit question per paragraph/scene of the outline or draft. Flags:

| Flag | Symptom |
|---|---|
| Linear interview | Each question follows administratively from the last (what happened → why → what resulted → what it means) |
| The reflection tail | Final paragraphs answer "what does this mean / how does she feel about it now" — the machine's closing move |
| Missing move types | No paragraph *compares* (two times, two characters, two versions of an event), none *verifies* (doubts or contradicts an earlier paragraph's account), none *digresses* (memory or association that earns its place later) |

**Fix:** Reorder so at least one question arrives before its setup. *(non-additive — runs in every operation, subject to edit scope)*

⊕ **Replace one consequence-paragraph with a comparison or a contradiction** *(additive where the comparison or contradiction is not already in the source — `write`/`recreate`, fiction only; emitted as a finding under `refactor`/`review`)* — LLMs use consequence/procedure moves ~19% of the time and comparison/verification moves ~0.2–0.3% (Q); a single "but that isn't how her sister remembers it" paragraph does more de-AI work than a page of rewording.

In non-fiction this move is legal **only** when the comparison or the dissenting account already exists in the source material. Supplying one the source does not contain is invention, not de-AI work — a postmortem does not get a contradicting account of the timeline because the discourse was too smooth. Where the material is genuinely absent, report the flat move-sequence and ask the author for it.

**Outline test (A):** extract the first sentence of every paragraph and read them as a list. If they form a clean summary of the piece, the structure is machine-shaped — a human outline has gaps, jumps, and sentences that make no sense out of context.

## 2 The middle is the choke point

Detectors and human judges find AI text most identifiable in the **body**, least in openings and endings — models imitate the formulaic bookends well and expose themselves in the long middle (T). LLM stories also show a measured mid-story collapse into predictable filler, rushing pace and leaving suspense unexplored (X, cited in narrative pass). Though this section speaks in fiction terms, the choke-point evidence was measured on news, essays, and email as well. **The extension to non-fiction covers the diagnostic half only** — the outline test and QUD check (§1), texture variance, and pacing — reading "scene" as section. **The additive fix below does not extend to non-fiction.** A non-fiction "event the opening does not predict" would be a claim or a finding that is not in the source, and supplying one is invention, not de-AI work. Diagnose the flat middle, report it as a finding, and ask the author for the missing material.

**Fix, aimed at the middle third:**

**Gate before you apply any of these.** The bullets split by whether they *add* material. An additive move is legal **only under `write` / `recreate` when the scene is `fiction`** — the same insertion rule `SKILL.md` §9 states. Under `refactor` and `review` an additive move is **not executed**: it is emitted as a finding awaiting the user's approval. **In non-fiction it does not apply at all, in any operation** — the truth-preserving contract forbids adding a claim or finding the source does not contain, and a flat middle never licenses supplying one.

- **[additive — `write` / `recreate`, `fiction` only]** Put at least one event there that the opening does not predict. Under `refactor` / `review`, report "the middle carries no unpredicted event" and stop there. In non-fiction, do not apply.
- **[non-additive — runs in every operation, subject to edit scope]** Vary texture between adjacent scenes: a dense scene then a fast one, a dialogue-heavy stretch then summary narration. Human writing shows high cross-paragraph variance ("burstiness"); models hold one register for the whole text (T). Rebalance what is already on the page rather than writing new material; under `bounded` you may not merge sentences or reorder paragraphs, and under `in-place` this is report-only.
- **[additive where it needs new material — then `write` / `recreate`, `fiction` only]** Let one thread slow down instead of resolving on schedule — the machine failure mode is acceleration past the interesting part. Where the slowdown can be had by cutting or deferring text that already exists, it is a non-additive edit and runs under `refactor` too, within scope.

## 3 Structural positions on the page

Position patterns survive paraphrase better than word choice does — after full paraphrasing, position tells became *more* visible to expert detectors, not less (R).

| Position tell | Machine habit | Human habit |
|---|---|---|
| Paragraph lengths | Uniform | Ragged — including a one-sentence paragraph |
| Quoted speech / key lines | Always closing a paragraph | Anywhere, including mid-paragraph |
| Lists of qualities, reasons, images | Exactly three items | Two, four, one — three sometimes |
| Scene transitions | Same connective formula each time | Varied: hard cut, time skip, dialogue pickup |
| Emphasis | Evenly distributed | Clustered where it matters, absent elsewhere |

## 4 Openings

The machine opening: establish time + place + weather, introduce the character with description, then start the story (B: "Once upon a time"-style detachment; R: the "On a drab November morning" scene-setting lead; S: AI over-grounds the opening spatially, 2.33 vs 2.12).

**Fix:** open inside the situation — mid-conflict, mid-conversation, mid-error ("Sam didn't know she wasn't human"). Ground space with one working detail, not a establishing shot. Delay the character's appearance-and-backstory paragraph indefinitely; most stories never need it.

## 5 Names

The tested model outputs converged on recurring names such as Elara, Ava, and Amelia; Emily or Sarah appeared in 63–70% of the AI articles, and formal titles were overrepresented (B, R).

**Fix:** name characters from the story's specific world (ethnicity, region, generation, class), let surnames and nicknames do social work, drop titles except where the fiction needs them, and let different characters call the same person different things.
