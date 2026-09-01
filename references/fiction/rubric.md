# Diagnosis rubric — the 30 core features

The behavioural contract single-source is `SKILL.md`. This file is a reference: where it and `SKILL.md` disagree, `SKILL.md` wins.

> ## SCOPE — every reference value here was measured on English ／ 適用範圍：本檔參考數值全部量測自英文語料
>
> ### EN
>
> - **The Human and AI reference columns come from English narrative corpora.** Neither parent skill carries a Chinese measurement baseline, so for a ZH-matrix text those numbers have nothing to calibrate against. *(grounded: the source study measures English narrative generation, and the absence of any Chinese baseline is a fact about these skills — not an estimate.)*
> - **For a ZH-matrix text, do not report the reference percentages, and do not report the Human/AI columns at all.** Not "~57% vs 82%", not "human ~3.3, AI 3.9", not an observed score placed beside a corpus number, not a hedged "above the AI reference". Every number in this file demotes to a qualitative prior the moment the matrix language is Chinese. *(inference: an English-measured value quoted against Chinese text reads as measurement and cannot be falsified — the worst kind of finding.)*
> - **The 30 features still route attention in Chinese — that is the whole of what they do there.** Read the five group headings as a list of places to look (thematic over-determination, embodied affect, structural tidiness, human-positive markers, temporal flatness). Whatever you find must then be stated in the Chinese inventories' own terms, and must survive with this file deleted. *(inference)*
> - **Report Chinese observations qualitatively, each carrying its quoted passage, and issue no aggregate verdict.** No score, no count, no group total, no combined leaning, no authorship probability. The Protocol and Reading rules below already forbid aggregation for English; that prohibition applies unchanged in both languages, and in Chinese it is the only reporting mode left. *(grounded, restating the existing prohibition)*
>
> **Where the Chinese-side rules live:** `references/fiction/narrative-pass.md` (Chinese transfer section) decides which of these narrative moves transfer to a ZH-matrix draft at all; `references/fiction/zh-fiction-surface.md` carries the Chinese surface inventory. On a Chinese text those two govern; this file only points.
>
> **Reread check (any review with a ZH-matrix span):** search your own report for a percentage, a Human/AI pair, or a numeric score. If one is attached to Chinese text, delete it and restate the observation qualitatively from a Chinese-side rule — or drop it.
>
> ### 中文
>
> - **本檔的 Human／AI 參考數值全部量測自英文語料。** 兩個母技能都沒有任何中文量測基準，中文母語文本因此無從對照。（grounded）
> - **中文母語文本一律不報這些百分比，也不報 Human／AI 兩欄。** 不寫「約 57% 對 82%」，不寫「人類約 3.3、AI 3.9」，不把觀察到的評分擺在語料數值旁邊，也不寫「高於 AI 參考值」這種含糊的說法。只要母語矩陣是中文，本檔的每個數字都降級成定性方向。（inference）
> - **30 項特徵在中文裡只負責指引查看方向。** 把五組標題當成「先看哪裡」的清單；看到什麼，仍要用中文清單自己的說法陳述，而且就算把本檔整個刪掉也照樣站得住。（inference）
> - **中文觀察一律定性陳述，逐條附原句引文，且不給任何總體結論。** 不算分、不計次、不做分組加總、不下綜合傾向、不換算成作者歸屬機率。下方的禁止加總規則中英文皆適用；在中文裡，定性陳述更是唯一可用的報告方式。（grounded，重申既有禁令）
> - **中文側規則以 `references/fiction/narrative-pass.md`（中文遷移一節）與 `references/fiction/zh-fiction-surface.md` 為準。** 面對中文文本時由那兩份主導，本檔只負責指路。
>
> **回讀檢查（凡是含中文母語段落的審閱）：** 在自己的報告裡搜尋百分比、Human／AI 數值對，以及任何評分。只要有一個掛在中文文本上，就把它刪掉，改由中文側規則以定性方式重新陳述；陳述不出來就整句不要。

The 30 narrative features below come from StoryScope's released taxonomy and corpus summary (AI-core and human-core tables 14–15; all-30 means and gaps, Table 16). StoryScope's Core Only 30-feature XGBoost held-out classifier reached 84.8% macro-F1 (AUPRC .828); this manual rubric is heuristic triage, not that classifier or an authorship detector. See [StoryScope arXiv v6](https://arxiv.org/abs/2604.03136v6) for the pinned study.

Use the Human and AI columns as corpus calibration references, not targets for an individual story. Observed signals are not authorship probabilities. This rubric makes no validated aggregate-detector or revision-threshold claim; any future aggregate claim requires a separate, documented evaluation.

## Protocol

1. Read **one group at a time**, in five separate passes. Never assess the whole rubric in one read: models self-evaluating text collapse onto one or two salient dimensions and go blind to the rest (measured on the slop taxonomy — span precision 0.13–0.16 across tested prompting conditions).
2. For each observed signal, quote the short passage that justifies it. No quote, no signal.
3. Record numeric, ordinal, and categorical observations beside the corpus references; do not convert them into authorship probabilities or a combined score.
4. Mark a feature **n/a** when the text offers no occasion to assess it, and record over-correction separately.

## Reading rules

| Case | Rule |
|---|---|
| Numeric rows (scale/ordinal) | Record the story's observed score and compare it qualitatively with the Human and AI corpus references. Do not apply a numeric cutoff. |
| Percentage rows (categorical/binary) | Record whether the AI-column option appears and quote its context. The corpus percentages are calibration context, not per-story probabilities or ratio cutoffs; absence of a human-leaning option is not itself a finding. |
| Group D | Record each human-positive marker separately with its quoted evidence. Do not collapse the markers into a group score. |
| Not applicable | A feature with no occasion in the text (no jeopardy → pre-threat investment; no reveal → recontextualization) is **n/a** and does not force a judgment. Reference explicitness is n/a only when the story makes no allusive gesture at all — an unnamed borrowed quotation or a recognizable unattributed retelling *is* an occasion (record it as implicit). Short texts produce several n/a — that is expected, not a defect of the story. |
| Over-correction | A numeric score at the far extreme *away* from the AI direction (e.g. discontinuity 5/5, thematic explicitness 1/5) → flag as **over-correction advisory**. Report it separately as a humanizer-fingerprint failure mode; do not reinterpret it as an AI-leaning signal. |

## Group A — Thematic over-determination (AI drifts high)

| Feature | How to judge | Human reference | AI reference |
|---|---|---|---|
| Thematic explicitness | 1 = themes stay implicit; 5 = thesis-like statements tell the reader how to interpret events | ~3.3 | 3.9 |
| Moral/philosophical weighting | How far ethical debate and thematic exposition outweigh story pleasure; check narrator commentary and climactic speeches | ~3.3 | 3.7 |
| Thematic unity | 5 = every scene, subplot, image reinforces one thematic core | ~4.4 | 4.7 |
| Narrator thematic commentary | Does the narrating voice generalize about what events mean ("That is how people are")? | yes in ~52% | 77% |
| Dialogue as philosophical debate | Do key dialogues argue ideas rather than advance want/conflict? | dominant in ~34% | 59% |
| Reference explicitness | Vague unnamed allusion as the dominant intertext mode (the human-leaning state is a balanced mix of named + implicit, 37% vs 16%) | implicit-only ~50% | 72% |

## Group B — Sensory & embodied performativity (AI drifts high)

| Feature | How to judge | Human reference | AI reference |
|---|---|---|---|
| Dominant emotion mode | Classify strong-affect scenes: explicit label / embodied sensation / behavior / ambiguous; flag embodied dominance as an AI-leaning signal | embodied dominant in ~38% | 81% |
| Setting as psychological mirror | Do weather/landscape/architecture consistently externalize inner states? | ~3.6 | 4.1 |
| Environmental emphasis | Landscape and ecology beyond backdrop | ~2.8 | 3.2 |
| Olfactory imagery | Smell among regularly engaged senses — judge salience relative to length (one prominent instance counts in flash-length text; recurring use in longer work) | ~57% | 82% |
| Sensory density | Proportion of text doing multi-sense description; 5 = lush, pace-slowing | ~3.7 | 3.9 |
| Depth of interior access | 1 = external only; 5 = stream of consciousness | ~3.7 | 3.9 |

## Group C — Structural streamlining (AI drifts high/tidy)

| Feature | How to judge | Human reference | AI reference |
|---|---|---|---|
| Causal-chain continuity | 5 = every event tightly linked in one line from incitement to end | ~3.9 | 4.2 |
| Subplots *(advisory signal)* | Absence of any subplot; too common in human stories (57%) to interpret without context | no-subplot ~57% | 79% |
| Resolution agency | Turning point triggered by protagonist choice vs chance/others | choice ~46% | 69% |
| Resolution mode | External act / internal acceptance / partial / open / catastrophic; flag internal acceptance as an AI-leaning signal | internal ~27% | 47% |
| Protagonist introduction | Device at first substantial appearance — one of: external description / in-action / in-dialogue / inner thought / others' reports. Flag external description as an AI-leaning signal; the other four are not signals by themselves (in-dialogue is the strongest human marker) | description ~30% | 52% |
| Opening spatial grounding | How completely the first scene fixes local + global place (1–4) | ~2.1 | 2.3 |
| Spatial granularity | Density of place names, rooms, routes (1–4) | ~2.3 | 2.5 |
| Pre-threat investment | Interiority/backstory built before jeopardy | ~2.8 | 3.0 |

## Group D — Human-positive markers

| Marker | How to judge | Human | AI |
|---|---|---|---|
| Named intertextuality | Any real text/author/work explicitly named | present in ~47% | 24% |
| Fourth-wall gesture | Any wink, aside, or reader acknowledgement anywhere | present in ~67% | 39% |
| Direct reader address | Any "you"/"dear reader" moment | present in ~28% | 7% |

## Group E — Temporal complexity & diversity (AI drifts low/tidy)

| Feature | How to judge | Human reference | AI reference |
|---|---|---|---|
| Chronological discontinuity | Frequency/sharpness of time jumps | ~2.4 | 2.1 |
| Anachrony intensity | Scene-level flashbacks/flash-forwards as structure | ~2.6 | 2.3 |
| Nonlinear framing for disclosure | Time devices used to stage revelations | ~2.0 | 1.7 |
| Recontextualization after surprise | How much earlier text a reveal recolors | ~3.3 | 3.0 |
| Location variety *(heuristic advisory)* | Optional editorial check: flag a 3,000+ word story that never leaves one locale unless the premise demands confinement | measured ordinal mean 1.34 | 1.08 |
| Dialogue proportion | Fraction of text in quoted speech (1 = none, 3 = balanced, 5 = dominates) | ~3.0 | 2.7 |
| Moral polarity toward protagonist | Narrative's final stance; flag a clearly affirmative or clearly condemning stance as an AI-leaning signal | ambivalent ~59% | clear 62% |

## Report format

Cite by quoting a short phrase, not by paragraph number. Keep the report descriptive: it records candidate signals for editorial review, not authorship probabilities or an aggregate action score.

```text
BE-HUMAN FICTION DIAGNOSIS — <title>
Scope: heuristic triage; corpus references only; no authorship probability or validated aggregate detector
Group A: observed signals …; n/a … (narrator commentary — "It was then she learned…"; …)
Group B: observed signals … (…)
Group C: observed signals …; n/a … (…)
Group D: marker observations … (named intertextuality present — "…")
Group E: observed signals … (…)
Advisories: over-correction …; subplots …; single-location …
Quoted evidence: <short phrase for each reported signal>
Plan: <ordered fixes, deepest layer first, each tied to a quoted passage>
```
