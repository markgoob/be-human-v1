# Pass 1 — Narrative architecture

Seven decision groups. Each lists the measured human-vs-AI gap, what to do when **generating**, and what to check when **revising**. Numbers are from StoryScope (S), Beguš 2024 (B), Xu et al. PNAS 2025 (X), Nonaka & Perry 2025 (N), and QUDsim (Q); percentages read *human vs AI*. Stable source identities live in the repository research ledger; single-letter aliases in this file are file-local. Generate/Revise prescriptions are Sepia design inferences unless a cited source explicitly tested the intervention.

Work through all seven groups when filling the architecture sheet, but **enact only 3–5 human-leaning moves per story** (see SKILL.md Calibration). The groups marked ⚑ were absent from the tools sampled in the repository's 2026-08-27 ecosystem snapshot; treat that as a bounded product observation, not proof of universal zero coverage.

## ⊕ Operation gate — read before any prescription below

Several prescriptions in this file **add material the source text does not contain**: insert an event with its own origin, braid in a subplot, plant a detail that never fires, give a character a relationship they did not have. Every one of them is legal **only** under operation `write` or `recreate` with scene `fiction`.

- Under `refactor` or `review`, never enact them. Emit each as a finding — name the gap, name the insertion you would make, hand it to the user, wait for approval. A `review` run reports; a `refactor` run edits what is already on the page.
- Under any operation on **non-fiction**, none of them apply at all.
- SKILL.md holds the contract (truth-preserving: never add facts); this is its local restatement, and SKILL.md governs where the two differ. An invented event is a fact about the story, and a story's facts belong to its author. The only insertion legal under every operation is real specificity already present in the text or supplied by the user.

**Generate:** blocks below assume `write`/`recreate`. **Revise:** blocks are what a `refactor` or `review` run reads; the additive lines inside them carry the ⊕ marker and the gate above. Everything else in this file is subtractive or rearranging — cut, convert, delete an edge, cool an edge, move a cause offstage, reorder, thin — and carries no operation gate, only the edit-scope limits (`bounded`: no merging sentences, no reordering paragraphs; `in-place`: no sentence deletion at all, report instead).

## Architecture sheet template

Fill this before drafting (Workflow A) or as the diagnosis summary (Workflow B):

| Decision | Choice for this story | Target band |
|---|---|---|
| Theme handling | stated / implied / withheld | implied by default |
| Subplot | none / parallel / contrasting / independent | one subplot, ~40% of stories |
| Resolution driver | protagonist choice / mixed / external | mixed or external ~50% |
| Ending mode | external act / internal acceptance / partial / open / catastrophic | avoid internal-acceptance default |
| Time structure | linear / moderate anachrony / braided | moderate (2–3 on a 1–5 scale) |
| Revelation pacing | front-loaded / even / back-loaded | back-loaded |
| Emotion strategy | mix of: explicit labels / behavior / embodied / ambiguous | behavior-led mix; embodied only at peaks |
| Protagonist introduction | description / in-action / in-dialogue / thought / others' reports | in-dialogue or in-action |
| Moral stance on protagonist | affirmative / tragic-flaw / ambivalent / antiheroic | ambivalent ~60% |
| Real-world anchors | list actual works, places, brands to name | ≥1 explicit named reference |
| Network shape | who never meets whom; who dislikes whom | sparse, net-neutral affect |
| Rarity move | the one structural choice atypical for this premise | exactly one |

## 1 ⚑ Theme: stop explaining it

| Feature | Human | AI |
|---|---|---|
| Narrator explicitly states the theme (S) | 52% | 77% |
| Thematic explicitness, 1–5 (S) | 3.28 | 3.94 |
| Dialogue used for philosophical debate (S) | 34% | 59% |
| Moral/philosophical weighting, 1–5 (S) | 3.26 | 3.68 |
| Thematic unity, 1–5 (S) | 4.41 | 4.74 |

**Generate:** Decide the theme, then trust the events to carry it. The narrator never summarizes the lesson; the grieving character's arc does **not** end with what she learned. Dialogue does plot and relationship work — characters argue about the rent, not about the nature of grief. Let one scene or image exist for texture alone, serving no theme (humans score 4.4/5 on unity, not 5/5 — near-total unity is the tell, total unity is worse).

**Revise:** Search the last three paragraphs and any narrator generalization ("That is how people are", "It was then she learned…", "In the end, what mattered was…") — cut or convert to a concrete action or image. Where dialogue debates ideas, rewrite so the disagreement is about something specific the characters want. If a symbol is explained in-text, delete the explanation and keep the symbol.

> Beguš reports recurring moralizing final lines such as "love knows no boundaries" in the tested model stories. Treat that pattern as a candidate signal, not evidence that a conclusive ending is necessarily machine-written.

## 2 ⚑ Plot: loosen the single track

| Feature | Human | AI |
|---|---|---|
| No subplots at all (S) | 57% | 79% |
| Subplot thematically parallel to main plot (S) | 42% | 21% |
| Causal-chain continuity, 1–5 (S) | 3.92 | 4.20 |
| Plot elements that reappear on regeneration — "drop ratio" (X) | 3.7% | 9–11% |

**Generate:** Give roughly two in five stories a subplot; when present, let it echo the main theme obliquely rather than restate it. Allow the causal chain to break once: an episode that isn't caused by the inciting incident, a consequence that arrives from offstage. ⊕ Plant one detail that never fires — humans leave loose ends; the fully-paid-off setup inventory is machine bookkeeping.

**Revise:** Outline the draft as a beat list. If every beat is caused by the previous beat in one unbroken line to the climax, sever one link — move a cause offstage. ⊕ Inserting an event with its own origin, or braiding in a second thread where the story has none and its length can carry one, **adds material**: legal only under `write`/`recreate` on fiction. Under `refactor`/`review`, write it up as a finding and wait for the user (see Operation gate).

**Echo test (X):** for each turning point ask — *if this premise were regenerated twenty times, would this same turn appear again?* The helpful stranger, the problem that solves cleanly, the reconciliation on schedule: these reappear. Replace inevitable turns with one that requires this story's particulars. Kafka's traffic cop says "Give it up!" and walks away; twenty regenerations produce twenty cops giving directions.

## 3 Endings and resolution

| Feature | Human | AI |
|---|---|---|
| Resolution driven by protagonist's own choice (S) | 46% | 69% |
| Resolution via internal understanding/acceptance (S) | 27% | 47% |
| Morally ambivalent protagonist (S) | 59% | 38% |

**Generate:** Do not default to the arc where the protagonist, having grown, chooses the resolution and makes peace with it — that compound default (agency + acceptance + growth) is the strongest ending fingerprint in the data. Half the time, let chance, other people, or institutions decide the outcome. Endings may be partial, open, or catastrophic. The protagonist's final moral position can stay mixed: vindicated in the event, wrong in the act.

**Revise:** If the draft ends with the protagonist deciding + accepting + understanding, change at least one leg of the tripod. Cut denouement paragraphs that settle every account; ending one beat *earlier* than feels complete is usually the fix.

## 4 ⚑ Time: linearity is a choice, not a default

| Feature | Human | AI |
|---|---|---|
| Chronological discontinuity, 1–5 (S) | 2.40 | 2.12 |
| Anachrony (flashback/flash-forward) intensity, 1–5 (S) | 2.58 | 2.31 |
| Nonlinear framing used to delay disclosure, 1–5 (S) | 1.96 | 1.68 |
| Recontextualization depth after a reveal, 1–5 (S) | 3.28 | 2.95 |
| Revelation pacing (human fingerprint, S) | back-loaded | even/front-loaded |

**Generate:** The human band is *moderate* nonlinearity — a story that opens at the funeral and spirals back through decades, not a shuffled puzzle-box. Use time jumps to **stage information**: hold back the cause, open with the effect. Aim reveals so they force rereading — the best twist recolors earlier scenes (target 3/5, not a twist that changes nothing and not a total inversion). Keep the biggest disclosure late (back-loaded pacing is a measured human fingerprint).

**Revise:** If the draft narrates first-cause-to-final-effect in order, find the scene whose impact grows when withheld and move it. Check that DeepSeek-style front-loading (all context delivered before the story starts moving) isn't present: cut the briefing, let context leak out mid-motion.

## 5 ⚑ Emotion and senses: break the show-don't-tell dogma

| Feature | Human | AI |
|---|---|---|
| Emotion conveyed mainly via embodied sensation/metaphor (S) | 38% | 81% |
| Emotion conveyed mainly via explicit labels (S) | 29% | 8% |
| Olfactory imagery among dominant senses (S) | 57% | 82% |
| Setting mirrors characters' inner states, 1–5 (S) | 3.58 | 4.07 |
| Sensory density, 1–5 (S) | 3.66 | 3.93 |
| Depth of interior access, 1–5 (S) | 3.67 | 3.93 |

**Generate:** AI executes "show don't tell" as dogma: fear is always a tightening chest, cold sweat, dimming lamplight. Humans mix four modes and lean on the plainest two — behavior first, plain naming second ("She was afraid" is a human sentence; models almost never write it). Reserve embodied rendering for one or two peaks per story. Let weather be weather: not every storm carries the marriage. Ration smell — it has become the connoisseur sense of machine prose.

**Revise:** Inventory every emotion beat and classify its mode. If embodied dominates, convert most to behavior (what she does) or plain statement (what she feels, named), keeping the strongest one or two embodied. Strip pathetic fallacy where the environment shadows mood scene after scene. Thin sensory description toward moderate density — cut the third sense in three-sense sentences.

## 6 ⚑ Characters and the social network

| Feature | Human | AI |
|---|---|---|
| Protagonist introduced via external description (S) | 30% | 52% |
| Human fingerprint: introduced in-dialogue (S) | strongest human marker | rare |
| Network density — share of character pairs that interact (N) | 0.18 | 0.34–0.47 |
| Mean relationship affect (N) | −0.06 (net neutral) | +0.24 to +0.66 (all positive) |
| Clustering among antagonistic ties (N) | 0.395 | 0.07–0.21 |
| Investment built before putting a character in danger, 1–5 (S) | 2.76 | 2.99 |

**Generate:** Bring the protagonist on stage talking or doing, not described ("The dog arrived on a Tuesday" beats a paragraph of appearance-and-backstory). Keep the cast graph sparse: some characters never meet; some know each other only through a third. Sum of relationship affect should sit near neutral — real casts contain dislike that has nothing to do with the plot. Give antagonism *structure*: the antagonist has allies, internal rifts, their own network — not a lone hostile node pointed at the hero. It's fine to endanger a character the reader barely knows.

**Revise:** Draw the cast graph with signed edges. If everyone connects to everyone, delete edges. If every edge is warm, cool several. ⊕ If the villain is isolated, giving them one relationship that doesn't involve the protagonist **adds material**: legal only under `write`/`recreate` on fiction. Under `refactor`/`review` it is a finding for the user, not an edit (see Operation gate).

## 7 ⚑ The outside world and the reader

| Feature | Human | AI |
|---|---|---|
| Explicit named references to real texts/authors (S) | 47% | 24% |
| Balanced mix of explicit + implicit reference (S) | 37% | 16% |
| Any fourth-wall permeability (S) | 67% | 39% |
| Direct reader address (S) | 28% | 7% |
| Distinct meaningful locations (S, ordinal) | 1.34 | 1.08 |
| Dialogue-to-narration proportion, 1–5 (S) | 2.95 | 2.70 |

**Generate:** Name real things — an actual novel on the shelf, a real band, the specific highway (accuracy rule in SKILL.md applies: only real, correct references; ask the user for material if needed). Mix named references with unnamed echoes. An occasional aside that admits a reader exists ("you know the kind of house") is a human move — *occasional*: an aside or two, not a metafictional frame. Let scenes happen in one or two more places than the premise strictly needs. Give dialogue slightly more floor than exposition.

**Revise:** If the draft gestures at "a famous poet" or "an old song," make one of them specific and real. If the story visits a single room for 5,000 words and the premise doesn't demand confinement, move one scene. Vague allusion everywhere = machine caution.

## The rarity move

Human stories are structurally *rarer* than AI stories (rarity percentile 0.71 vs 0.49; the five models cluster in one region of narrative space and humans scatter). Beyond the band-calibrated rules above, make **exactly one** structural choice that is genuinely atypical for the premise — an unexpected narrator distance, a resolution mode the genre rarely uses, a frame that recasts the genre (crossover literary ambition is a measured human fingerprint). One. More than one reads as performance.

---

# 中文小說：逐項移轉判定（整節 INFERENCE）

上面每一個數字都測在英文語料上。原樣搬進中文，它們會變成一組講得很有把握、卻無法被推翻的數字——那正是 `rubric.md` 的協定要擋的東西。但架構層不是只有數字：每一條規則底下還有一個**問題**，而問題是跨語言的。這一節保留問題，丟掉數字。

兩個母技能都沒有中文語料測量：沒有人類／模型對照樣本，沒有標註實驗，沒有分布。所以**整節 `inference`**。以下逐項只給移轉判定與觀察動作，不給任何中文門檻。

## 硬性規則

- **不引用參考百分比。** 上文的百分比與量表分數屬於英文語料。中文回報裡一個都不出現，也不換算、不取近似、不說「大約」。
- **不列人類／AI 兩欄。** 中文側沒有 AI 欄可以填。
- **不給總體判定。** 不加總、不計分、不推論作者身分。特徵清單的作用是**指路**（該看哪裡），不是**發照**（可以下判斷）。
- **每一項觀察必須引出原文。** 沒有引文的觀察不成立，也不得計入風格預算。
- **先判編輯範圍再判內容。** 本節的動作幾乎全是結構動作：`structural` 可直接改寫、移動、刪場景；`bounded` 只能句內處理，移動或刪除整場一律進使用者確認清單；`in-place` **只回報**。範圍是 `in-place` 時本節整節降為觀察報告——這是常態，不是失敗。
- **不替作者發明。** 小說裡的「事實」是作者的設定。**本節不新增事實；結構性插入（插入事件、織入副線、留一個不回收的細節、給人物一段新關係）僅在 `write` / `recreate` 且場景為 `fiction` 時合法**；操作是 `refactor` / `review` 時，這些一律只寫成待使用者確認的建議，不逕自加進文本。其餘情況本節的動作只有「拆」與「移」；需要補的具體材料只能來自原文或使用者。

## 移轉總表

| 特徵 | 中文判定 | 產出 |
|---|---|---|
| 結局主導權（決定／接受／明白三腳架） | 移轉 | 質性觀察 |
| 因果鏈斷裂 | 移轉 | 質性觀察 |
| 揭露後置 | 移轉 | 質性觀察 |
| 時序不連續 | 移轉 | 質性觀察 |
| 人物網稀疏度與關係正負 | 移轉 | 帶正負號的關係圖 |
| 主角登場方式 | 移轉 | 分類；只有外觀描寫算訊號 |
| 副線有無 | 移轉（提示級，單獨不成標記） | 質性觀察 |
| 單一場景封閉 | 移轉（八條裡最弱的一條） | 質性觀察 |
| 敘事者明說主題、抒情收尾 | 歸表層 | `zh-fiction-surface.md` §2.5 |
| 情緒模式配比、成語化情緒 | 歸表層 | 同上 §3 |
| 嗅覺主導、天氣收尾、借景抒情 | 歸表層 | 同上 §2.7、§2.6、§3 |
| 具名互文 | `n/a` | — |
| 直接稱呼讀者、第四面牆 | `n/a` | — |
| 道德立場曖昧 | `n/a` | — |
| 對話比例 | `n/a` | — |
| 開場空間定位、空間細節密度 | `n/a` | — |
| 危險前投資 | `n/a` | — |
| 稀有度百分位 | `n/a`（動作保留） | 正好一個非典型結構選擇 |
| 對話用來辯論理念 | 移轉（提示級，單獨不成標記） | 質性觀察；併入「敘事者明說主題」那一次標記 |
| 主題統一度 | 移轉（不設門檻、不計數） | 一個動作：允許一個場景或影像不服務主題 |
| 道德／哲學比重 | `n/a` | — |
| 感官密度 | `n/a` | — |
| 內心進入深度 | `n/a` | — |

上表最後五列是**補判**：英文表裡有、原本沒進總表的特徵，一律在這裡給出判定，不留空白。它們與本節其餘部分同屬 `inference`——沒有中文語料測量，只給移轉判定與觀察動作，不給門檻。理由各一句：

- **對話用來辯論理念**：「這段對話在辯抽象，還是在爭一件具體想要的東西」是跨語言的問題，所以移轉；但論道、講經、公案問答、師徒答問在中文是形式，判前先確認語體，因此只到提示級，也不另立條目。
- **主題統一度**：統一度本身不評分、不設門檻，理由見下段；真正要處理的是敘事者替讀者把主題講出來，那件事歸表層 §2.5。
- **道德／哲學比重**：量表刻度在中文沒有錨點；勸懲與寓意在章回、寓言、公案裡是形式配備，比重高低落在語體之間，不落在作者身分之間。
- **感官密度**：刻度在中文沒有錨點，兩端差距也不到一個刻度；密度高低由語體與類型決定（純文學稀、網文密），就算判了也改不動任何一句話。
- **內心進入深度**：同上；中文的內心進入深度由人稱與語體決定（第三人稱限知、說書體的外視角），不是作者身分的訊號。

結構層對「主題統一」只留一句、不設門檻、不計數：**允許一個場景或一個影像不服務主題**。要處理的是「敘事者替讀者把主題講出來」，那件事在表層被 §2.5 抓，不在這裡重複收費。

## 1 結局主導權

**這是整個 fiction 套件裡價值最高的一條。只改得動一件事的時候，改這一件。**

- **訊號**：結尾同時滿足三件事——主角自己做了決定、主角在內心接受了它、主角因此明白了什麼。三腳架站齊就是訊號；缺一隻腳就不是。
- **預設動作**：拆掉至少一隻腳。讓機運、別人、或制度（公司、家族、法院、學校、戶政）決定結果；或讓主角決定了卻沒有接受；或讓他接受了卻沒有明白。結局可以是部分的、開放的、崩壞的。
- **中文特有的落點**：三腳架在中文常由一句話收束——「他終於懂了」「他放下了」「這一次他沒有再回頭」。那一句同時是表層 §2.5 的命中；**合併為一次標記，不重複計入預算**。
- **保留條件**：類型形式要求三腳架（成長小說、勵志、少年少女讀物、明確指定的委託目標）；使用者要求圓滿收束。
- **重讀檢查**：把最後一段刪掉，倒數第二段收不收得住？通常收得住，而且更好。收不住的時候，缺的是事件，不是結論——回去補事件，不要換一句抽象的填回來。

## 2 因果鏈斷裂

- **訊號**：每一場戲都由前一場推動，一路直達高潮，沒有一件事來自故事外部；每一個伏筆都有回收。
- **預設動作（只拆與移）**：把其中一個環節的原因移到場外——事情在別處已經發生了，人物只是接到了結果。範圍是 `structural` 才動得了場次；`bounded` 只列清單；`in-place` 只回報。
- **⊕ 增補動作（操作與範圍雙重限制）**：插入一個自帶來源的事件，或留一個從頭到尾沒有回收的細節，這兩件都是往故事裡加東西——**只在 `write` / `recreate` 且場景為 `fiction` 時做**；`refactor` / `review` 只把它寫成一條待使用者確認的建議，範圍限制照樣另外成立。
- **回聲測試（質性版）**：對每一個轉折問——同一個前提交給二十個人寫，這個轉折會不會二十次都出現？路過的好心人、剛好解開的誤會、按時到來的和解，會。英文那邊有一個重複率數字，**那個數字不隨語言走，中文側不得引用**；能用的只有這個提問。
- **保留條件**：推理、解謎、公案類型——線索全部回收是形式契約，不是機器痕跡；極短篇沒有空間分岔。
- **重讀檢查**：斷開之後，讀者接不接得上？接不上就是斷錯地方，不是斷太多。

## 3 揭露後置

- **訊號**：最重的一次揭露落在前三分之一；或開場先把來龍去脈交代完（設定簡報）才開始動。
- **預設動作**：把簡報拆散，讓背景在動作中漏出來；把最重的揭露往後挪。先給結果，後給原因。
- **保留條件（重要的誤殺防護）**：說書體、章回體的「話說……」式開場交代是**形式**，不是前置簡報；倒敘結構本來就先給結果。判之前先確認語體。
- **重讀檢查**：挪動之後，前面的場景有沒有被重新上色？沒有的話，那個揭露本來就不重要，挪了也沒用。

## 4 時序不連續

- **訊號**：全篇嚴格線性、沒有一次時間跳接，而題材承載得住。
- **預設動作**：只做**中度**——一到兩次跳接，用來藏資訊，不做拼圖式的打散。
- **中文特有的檢查點**：中文沒有時態，時間跳接全靠時間詞、場景分隔與人稱視角標示。跳完之後**讀者定不定得住位**，是中文比英文更容易失手的地方；定不住就補一個時間錨（那年冬天、搬家之前、他還在念書的時候），不要靠讀者推。
- **保留條件**：篇幅太短撐不起跳接；意識流語體本來就在跳。
- **重讀檢查**：這次跳接是為了藏東西，還是為了顯得複雜？後者退回線性。

## 5 人物網稀疏度與關係正負

- **訊號**：每個角色都跟每個角色見過面；所有關係都是善意的；反派是一個孤立的敵意節點。
- **預設動作（只拆與移）**：刪掉幾條邊（有些人從頭到尾沒見過面，有些人只透過第三人認識）；把幾條邊調冷——真實的人群裡有跟情節無關的不對盤。
- **⊕ 增補動作（操作與範圍雙重限制）**：給反派一段與主角無關的關係，讓敵意也有自己的結構。這是**新增素材**，只在 `write` / `recreate` 且場景為 `fiction` 時合法；`refactor` / `review` 下只寫成待使用者核可的建議，不逕行寫入。edit scope 的限制另外獨立適用。
- **只標記全正，不標記密**：中文長篇（家族小說、群像、宅門）人物多而關係網密是**題材**決定的，不是痕跡。密度本身不標記；**所有邊都是正的**才標記。
- **保留條件**：封閉群像（暴風雪山莊、獨幕劇）本來就要求全員互見。
- **重讀檢查**：畫一張帶正負號的關係圖。全部是正號，或反派只有一條指向主角的邊，就是要動的地方。

## 6 主角登場方式

- **訊號**：主角第一次實質登場，是一段外觀加身世的描寫。**只有這一種算訊號**；在說話、在做事、在想事情、由別人轉述，四種都不算。
- **預設動作**：改成在說話或在做事的時候登場。
- **保留條件**：章回體、武俠的定場詩與人物贊是形式；言情、網文的開場外貌描寫是類型期待，判前先確認語體。
- **重讀檢查**：把那段描寫刪掉，讀者還認不認得出他是主角？認得出，描寫就是多的。

## 7 副線有無

- **訊號**：全篇只有一條線，而篇幅撐得住第二條。
- **提示級，單獨不成標記**：只有一條線在人類作品裡本來就常見，不能拿來當判準；它只在跟其他觀察一起出現時才有意義。
- **⊕ 預設動作（新增素材，操作與範圍雙重限制）**：織入一條側面呼應主題的線——**呼應，不是複述**。副線把主題再講一次，等於把主題講了兩遍。
  　　織入副線是**新增素材**，只在 `write` / `recreate` 且場景為 `fiction` 時合法。`refactor` / `review` 下的動作只到「回報全篇單線、篇幅撐得住第二條」為止，等使用者決定。edit scope 的限制另外獨立適用。
- **保留條件**：極短篇、獨幕、單一事件的作品。
- **重讀檢查**：第二條線有沒有自己的結束？沒有就是裝飾，收掉。

## 8 單一場景封閉

- **訊號**：長篇幅從頭到尾不離開一個房間，而前提沒有要求封閉。
- **八條裡最弱的一條**：它在英文側本來就只是編輯提示，中文側更弱。**永遠排在最後**，預算不夠時第一個放掉。
- **預設動作**：把一場戲移到別處。
- **保留條件**：前提就是封閉（牢房、太空艙、守靈、颱風夜）。
- **重讀檢查**：移出去之後有沒有新增資訊？沒有就退回原地。

## 判 `n/a` 的條目

在中文基準出現之前，以下條目**不判、不記、不佔預算**。每項一句理由：

- **具名互文**：要判密度得先有一個中文參考池（哪些作品、作者、品牌算「可指名且讀者認得」，還會隨地區浮動），兩個母技能都沒有；指名真實事物仍然是好寫法，只是不作為判準。
- **直接稱呼讀者、第四面牆**：章回小說的「看官」「話說」「且聽下回分解」，加上現代網文的「作者有話說」，讓敘事者向讀者說話在中文裡是**語體慣例**。英文那個對比測的是一個罕見動作，中文裡它是常見形式——用它當人類痕跡會誤判整個說書傳統，用它當機器痕跡更荒謬。兩個方向都不成立，因此不判。
- **道德立場曖昧**：公案、武俠、章回的善惡有報是形式要求，把「立場明確」讀成機器傾向會削掉整個類型。
- **對話比例**：中文對話占比由語體決定（網文密、純文學稀），差距落在語體之間，不落在作者身分之間。
- **開場空間定位、空間細節密度**：英文量表的刻度在中文沒有錨點，而且兩端差距不到一個刻度——就算判了也改不動任何一句話。
- **危險前投資**：同上；中文短篇常以極少鋪陳直接進事件，那是文體選擇。
- **稀有度百分位**：百分位需要一個中文敘事空間的分布才算得出來，不存在。但**動作**不含門檻，保留：整篇做**正好一個**對這個前提而言不典型的結構選擇。一個。兩個就變成表演。

## 與表層清單合跑

本節與 `references/fiction/zh-fiction-surface.md` 是**同一次檢查的兩層**，一起跑，不分兩次交件。順序：

1. Layer 1 台灣用語與標點正確性（永遠生效，不佔風格預算）。
2. **本節**：結構觀察，由深到淺。
3. `zh-fiction-surface.md` 的表層清單。

風格預算（3–5 個動作）由兩層**共用**。搶不過來的時候，結構優先於表層——動一次結局主導權，抵過三次明喻密度。但編輯範圍是 `in-place`、結構動作全部不合法時，預算改花在表層，本節只回報。

兩層打到同一處時**合併為一次標記**：結局三腳架的收尾句同時是 §2.5 的抒情收尾公式；天氣收尾同時是 §2.6 與 §3 的機械鏡射。重複計費會把預算吃光，而且看起來像是問題有三個。

本節內部的取捨順序：結局主導權 ＞ 因果鏈 ＞ 揭露後置與時序 ＞ 人物網 ＞ 登場方式 ＞ 副線 ＞ 單一場景。

## 回報形狀

```text
中文小說結構觀察 — <篇名>
範圍：結構診斷，無中文基準；不給總體判定，不推論作者身分
結局主導權：<觀察>（引文「…」）
因果鏈：<觀察>（引文「…」）
揭露位置與時序：<觀察>（引文「…」）
人物網：<帶正負號的觀察>
登場方式：<分類>（引文「…」）
副線：<有／無，提示級>
場景數：<觀察>
n/a：具名互文、讀者稱呼、道德立場、道德哲學比重、對話比例、空間、感官密度、內心進入深度、危險前投資、稀有度百分位
表層（見 zh-fiction-surface.md）：<合併後的標記>
編輯範圍：<structural／bounded／in-place>；本次動作 <n>／預算 3–5
處理順序：<由深到淺，每一條綁定引文>
```

回報裡不出現百分比、不出現人類／AI 對照、不出現總分。出現了就是這一節被跳過了。
