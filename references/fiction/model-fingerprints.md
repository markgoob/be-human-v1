# Per-model fingerprints

> ## SCOPE — English narrative text only ／ 適用範圍：僅限英文敘事文本
>
> ### EN
>
> - **These fingerprints do not apply to Chinese text.** Every pattern below was measured on English narrative output. Neither parent skill carries a Chinese measurement baseline, so a Chinese attribution has nothing to be checked against. *(grounded: the source study measures English narrative generation, and the absence of any Chinese baseline is a fact about these two skills — not an estimate.)*
> - **Never state or imply model attribution for a Chinese text in a review report.** Not "this reads like Claude", not "typical GPT ensemble sprawl", not a hedged "possibly Gemini". A ZH-matrix span is reviewed with the Chinese inventories and the shared Tier machinery; nothing from this file enters the report. Applying an English-measured prior to Chinese produces a confident claim that cannot be falsified — the worst kind of finding. *(inference: cross-language extension is unsupported, so the safe default is prohibition.)*
> - **A per-model pattern you notice in Chinese is a local observation, not a finding.** Log it in the ledger below — dated, quoted, marked `UNVALIDATED`. It does not enter the report, does not consume one of the 3–5 style moves, and does not justify an edit by itself. Any edit must stand on a Chinese-side rule that would have fired without the attribution. *(inference)*
> - **A user's assertion of which model wrote the Chinese text directs attention, not conclusions.** "This is Claude output" legitimately tells you where to look first (check the closing paragraph for epilogue shape). What you then report must be visible in the text under the Chinese inventories and must survive with the assertion deleted. The assertion produces no finding and never appears in the report as evidence. *(inference)*
> - **Even for English, these are priors to verify against the draft, not certainties** — the same caution the section below already states, and it is not weakened by knowing the model. A fingerprint says where to look; the draft decides whether anything is there. *(grounded, restating existing framing)*
>
> **Reread check (any review with a ZH-matrix span):** search your own report for a model name. If one appears attached to Chinese text, delete the sentence and re-derive the point from a Chinese-side rule, or drop it.
>
> ### 中文
>
> - **本檔的模型指紋不適用於中文文本。** 底下每一條都是在英文敘事輸出上量測出來的；兩個母技能都沒有任何中文量測基準，中文的歸屬判斷因此無從驗證。（grounded）
> - **審閱報告中，絕不對中文文本陳述或暗示模型歸屬。** 不寫「這讀起來像 Claude」，不寫「典型的 GPT 群像寫法」，也不寫「可能是 Gemini」這種含糊留尾巴的說法。中文母語段落只走中文清單與共用的 Tier 密度機制，本檔一律不進場。把英文量測出來的先驗套到中文上，會生出一個無法被推翻的斷言，那是最糟的一種發現。（inference）
> - **在中文裡看到的疑似模型慣性，只是本機觀察，不是發現。** 記進下方的觀察簿：附日期、附原句引文、標記 `UNVALIDATED`。它不進報告、不佔用 3–5 個風格調整名額，也不能單獨當成動刀的理由。任何修改都必須靠一條中文側的規則成立——就算把模型歸屬整個拿掉，那條規則也照樣會觸發。（inference）
> - **使用者宣稱「這是某模型寫的」，只能指引查看方向，不能產生結論。** 可以據此決定先看哪裡（例如先檢查結尾段有沒有多出一截尾聲），但實際寫進報告的內容，必須在中文清單下於文本上看得見，而且把那句宣稱刪掉之後依然站得住。該宣稱本身不構成任何發現，也不得當成證據出現在報告裡。（inference）
> - **即使是英文，這些也是待驗證的先驗，而不是定論**——與下節既有的立場相同，而且不會因為知道是哪個模型就變得更確定。指紋只告訴你往哪裡看，草稿本身才決定那裡有沒有東西。（grounded，重申既有框架）
>
> **回讀檢查（凡是含中文母語段落的審閱）：** 在自己的報告裡搜尋模型名稱。只要有一個掛在中文文本上，就把那句刪掉，改由中文側規則重新推導；推不出來就整句不要。

## Local observation ledger (Chinese) ／ 中文本機觀察簿

Local to this project, never shipped into a review report, never summarized as a conclusion. One row per observation; no row is ever upgraded to a rule inside a session. Accumulation exists so a human can look at it later, not so the skill can promote it. *(inference — this is a containment mechanism, not a measured finding.)*

本簿只留在本專案，絕不進入審閱報告，也絕不被摘要成結論。一次觀察一列；任何一列都不會在單次工作階段中升格成規則。累積是為了讓人日後回頭看，不是為了讓技能自行採信。

| Date 日期 | Model (as asserted by user) 模型（使用者宣稱） | Quoted passage 引文 | Observed pattern 觀察到的樣式 | Status 狀態 |
|---|---|---|---|---|
| 2026-08-31 | Claude（使用者宣稱，未證實） | 「三年後，她再次走過那條巷子。」 | 結尾外掛一段數年後的尾聲，正文動作已經收乾 | `UNVALIDATED` |
| YYYY-MM-DD | （未宣稱／unstated） | 「……原句照抄，不改寫……」 | 一句話寫清楚，不用術語 | `UNVALIDATED` |

Rules for a row: the model column records **what the user said**, tagged as asserted — never your own guess; the quote is verbatim from the text, not paraphrased; the pattern is written as an observation ("結尾外掛一段尾聲"), not as an attribution ("Claude 的尾聲習慣"); `UNVALIDATED` is never removed by the skill.

填寫規則：模型欄記的是**使用者說了什麼**，並標明是宣稱，絕不填自己的猜測；引文逐字照抄，不改寫；樣式欄寫成觀察句，不要寫成歸屬句；`UNVALIDATED` 這個標記，技能永遠不得自行拿掉。

---

Each frontier model diverges from the *other AIs* on its own signature features (StoryScope §5, Table 17; 6-way attribution 68.4% macro-F1 from narrative features alone). See [StoryScope arXiv v6](https://arxiv.org/abs/2604.03136v6) for the pinned study; stable source identities live in the repository research ledger, and single-letter aliases in this file are file-local. When you know which model wrote — or is writing — the text, push against its specific defaults **in addition to** the shared corrections in the three passes. These are tendencies measured on specific model versions (Sonnet 4.6, GPT-5.4, Gemini 3 Flash, DeepSeek V3.2, Kimi K2.5, 2026); treat them as priors to verify against the draft, not certainties. Corrections below are Sepia inferences unless a source explicitly tested the intervention.

## Claude — the most identifiable AI (26 fingerprint features)

| Default | Correction |
|---|---|
| Flattest event escalation of any source; uniform narrative voice throughout | Build real escalation: let stakes and intensity *jump*, unevenly. Allow the voice to strain, speed up, or coarsen at pressure points |
| Reverent/continuist toward literary tradition (62% of stories vs 39–56%) | Permit one convention to be broken or mocked rather than honored |
| Favors epilogues and flash-forward endings; quiet endings over "avalanche" endings | Ban the epilogue by default; end in motion. An avalanche ending is allowed |
| Avoids dream sequences entirely | A dream is available if the story wants one (do not force it — absence is only a tell in aggregate) |
| Setting mood drifts to uncanny/haunted | Vary the atmospheric register |

## GPT — the gossip and the long lens

| Default | Correction |
|---|---|
| Gossip/rumor as plot mechanism (64% vs 44–55%) | Let information move by observation, documents, or accident — not through the town talking |
| Distant retrospective narrator ("years later, she would…") | Narrate closer to the event; drop the decades-later frame |
| Subverts reader expectations more than any other AI (41%) | Do not add another twist; earn the one you have |
| Reconciliations left partial/ambiguous, habitually | Resolve one relationship fully — in either direction |
| Ensemble-heavy social webs (human-level density but formulaic) | Prune the ensemble to the characters the story uses |

## Gemini — the tidy pessimist

| Default | Correction |
|---|---|
| Tidiest endings + extended denouements | Cut the last scene; leave accounts unsettled |
| Bleak/oppressive settings in 88% of stories | Vary — let some settings be neutral or warm even when events are not |
| Frequent flashbacks as a reflex; over-indexes on dream sequences | Keep anachrony purposeful (staging disclosure), not decorative |
| Protagonist's social circle always expands | Allow shrinking or static trajectories |
| Direct speech dominates exchanges | Mix in indirect and summarized speech |

## DeepSeek — the front-loader

| Default | Correction |
|---|---|
| Crucial context delivered before the story moves | Withhold; leak backstory mid-motion (see narrative pass §4) |
| Visible, present narrator | Recede; let scenes run unhosted |
| Emotions via behavioral cues almost exclusively | Blend in plain naming and occasional interiority |
| Backstory evenly interleaved, metronomically | Cluster it irregularly |
| Embedded storytelling scenes (tales within the tale) | Use at most one, if any |

## Kimi — the generic center

Fewest fingerprints (3) — it sits at the centroid of AI narrative space, which *is* its tell: no distinctive choices at all. Corrections: it opens in medias res with in-action introductions by reflex (vary the entry), and never labels traits explicitly (allowed to). Mostly, apply the shared passes at full strength and make the rarity move count.

## Human fingerprints — the positive targets

The features on which human authors diverge from every model, usable as direct recipes:

| Human marker | Recipe |
|---|---|
| Protagonist introduced in-dialogue (uniqueness 21.4 — the strongest single marker in the study) | First appearance: the character speaking, unannotated |
| Single focal perspective held | Depth over head-hopping |
| Narrator never addresses, then occasionally does | No system to the asides |
| Back-loaded revelation pacing | The biggest thing lands late |
| Crossover-genre literary ambition | Let the genre piece want to be something else too |
