# 來源與授權

`be-human-v1` 是三個上游專案的合併衍生作品，於 2026-08-31 合成。

## 上游

| 來源 | 作者 | 授權 | 版本 |
|------|------|------|------|
| [shuorenhua](https://github.com/MrGeDiao/shuorenhua) | MrGeDiao | MIT | v2.3.1 |
| [de-ai-tone](https://github.com/allenloves/de-ai-tone) | allenloves | **CC BY-SA 4.0** | commit `495a7f0` |
| [sepia](https://github.com/Nanako0129/sepia) | Nanako Tsai | MIT | v0.4.0 |

授權全文分別見 `LICENSE-shuorenhua-MIT`、`LICENSE-de-ai-tone-CC-BY-SA-4.0`、`LICENSE-sepia-MIT`。

前兩者先前已於 2026-08-21 合併為本機版 shuorenhua；本次再與 sepia 合併。

## 授權上的後果

**整體採 CC BY-SA 4.0。** 根檔 `LICENSE` 即為此授權。

理由：de-ai-tone 的 CC BY-SA 4.0 帶 share-alike 條款，而它的內容已不可分割地併入 `references/taiwan-usage.md`、`references/punctuation.md`、`references/translation.md` 與 `references/structures.md`。share-alike 因此擴散到整份合併作品。MIT 允許被再授權為 CC BY-SA，反向不成立，所以三方合流的唯一合法出口就是 CC BY-SA 4.0。

對外散布時必須：

- 整體標示 CC BY-SA 4.0，不能只掛 MIT
- 具名三位原作者：MrGeDiao、allenloves、Nanako Tsai
- 保留本檔與四份 LICENSE 檔
- 註明改作自上述三個專案

本機自用不涉及散布，不受此限；但本專案已按可發布的標準組織。

## 檔案出處對照

### 來自 de-ai-tone（CC BY-SA 4.0）—— share-alike 的來源

| 檔案 | 對應條目 | 本次改動 |
|------|------|------|
| `references/taiwan-usage.md` | §14 高頻對照表、§15 表外詞判斷、§16 英文命名禁音譯 | 原樣 |
| `references/punctuation.md` | §17 全形與半形、§18 引號、§3 冒號 | **新增語言邊界一節**，原有第 4 節掃描清單編號保留 |
| `references/translation.md` | §12 歐化句式、§13 慣用直譯句型、§10 贅詞量詞、§11 框式介詞 | **新增來源判定與 ZH→EN 方向** |
| `references/structures.md` 第 26 條 | §7 版面裝飾（emoji、小標題門檻、加粗上限） | 併入合併後的結構檔 |

### 來自 shuorenhua（MIT）

骨架來自這裡：場景判定、Tier 分級、力度檔位、edit scope、protected spans、輸出合同、兩道回讀、量化回退門檻。

`references/` 下**原樣沿用**：`phrases-zh.md`、`positive-style.md`、`operation-manual.md`、`boundary-cases.md`、`examples.md`。

**改動過的**：

| 檔案 | 改了什麼 |
|------|------|
| `protected-spans.md` | 加入兩條 sepia 條目（對白與世界內文件不得規整化、作者已確認的用語習慣） |
| `structures.md` | 逐條合併 sepia 的英文文法條目並加語言標籤；第 18 條補上 edit scope 降級梯；新增檔案層級的 scope 聲明 |
| `severity.md` | 新增「計數約定」一節；第 11 條改寫，ZH-matrix 內的英文改判語言路由第 5 節 |
| `scene-guardrails.md` | 新增 `fiction` 場景的禁改條款（該場景是本次合併新增的） |
| `packs/_scene-packs-zh.md` | README 包新增「保留路徑不等於保留錯的路徑」條款，接到 professional-pass 的 check 11；**新增 `commit-message` 場景包**（commit 訊息與 PR 內文，含硬性署名規則），此包兩個上游都沒有 |
| `evals/real-samples.md` | 僅修正一處簡繁過度轉換（`一箇`→`一個`） |

全部檔案先前已由簡體轉為臺灣繁體，並修正過度轉換與選字錯誤。2026-09-01 又補修三處殘留（`一箇` 兩處、`隻是` 一處）。

### 來自 sepia（MIT）

診斷內容來自這裡：小說敘事架構、專業場地知識、英文詞彙庫、語料取樣、安全邊界。

**原樣沿用**：`references/style-pass.md`、`references/packs/en-*.md`、`research/`（僅修正指向舊 repo 版面的相對連結）。

**改動過的**：

| 檔案 | 改了什麼 |
|------|------|
| `references/fiction/narrative-pass.md` | 新增中文轉換一節；新增檔首的 operation gate；三處新增型處方逐一標記 |
| `references/discourse-pass.md` | 新增禁用於中文的 SCOPE 聲明（§5 英文人名清單完全不跑中文）；§1 與 §2 的新增型處方加上 operation gate；§2 對非虛構的延伸限縮到診斷半邊 |
| `references/fiction/rubric.md` | 新增禁用於中文的 SCOPE 聲明；報告標頭改為 be-human；保留其禁止加總條款不動 |
| `references/fiction/model-fingerprints.md` | 新增禁用於中文的範圍聲明 |
| `references/professional-pass.md` | 改為雙語；改用 Tier 門檻取代定性說法；加入語料取樣與第 1 層的互動條款；**新增 check 11 可攜性**（絕對路徑只在作者機器上成立）與**工具署名／署名 trailer 專節**，這兩條兩個上游都沒有 |

`references/phrases-en.md` 是**兩個上游合併**而成，不單屬 sepia：Tier 骨架與專業文體條目來自 shuorenhua 的 `phrases-en.md`（MIT，MrGeDiao），詞彙內容以 sepia 的 `style-pass.md` 為主（MIT，Nanako Tsai）。兩份都是 MIT，具名時兩位都要列。

### 本次合併新寫

以下內容不屬於任何上游，是合併後才成立的：

| 檔案 | 為什麼只有合併後才需要 |
|------|------|
| `SKILL.md` | 新的綜合。結構承自 shuorenhua 的 SKILL.md，但三層啟用、雙軸路由、操作×力度×scope 三軸參數化與 calibration 兩半都是新的 |
| `references/language-routing.md` | 兩邊都沒有宣告語言範圍。sepia 從未說自己只管英文，shuorenhua 只說「繁體中文的連續文字」而沒說旁邊的英文段落怎麼辦 |
| `references/fiction/zh-fiction-surface.md` | shuorenhua 沒有 fiction 場景且對文學場景放行，sepia 的小說病灶表是英文詞彙 —— 中文小說在兩邊都掉下去 |
| `references/packs/zh-postmortem.md`、`zh-ticket.md`、`zh-tech-article.md`、`zh-code-review.md` | 這四個場景只有英文版；直接翻譯會從事故詞彙把支語帶進來，而那正是第一層要擋的 |
| `references/whitelists.md` | 兩邊的誤殺防護清單接近互斥，需要合成一份並逐條標語言 |
| `README.md` | 合併版的說明檔，兩個上游都沒有對應物 |

## 處理過的規則衝突

前一次合併（shuorenhua + de-ai-tone）處理過一件：`structures.md` 第 20 條要求把過密的破折號改成冒號，而 de-ai-tone §3 禁止冒號當萬用連接詞。處理方式是第 20 條保留預設動作但加註受 `punctuation.md` 第 2 節約束。該處理沿用至今。

本次合併（+ sepia）處理了四件真衝突。27 個接觸點裡其餘的是重複或互補。

| 衝突 | 處理 |
|------|------|
| sepia 的小說處方要求插入（種一個永不引爆的細節、加一個未預示的事件），與保真合同「不得新增事實」直接牴觸 | 依操作開關：插入只在 `write` 與 `recreate` 且場景為 `fiction` 時合法；`refactor` 與 `review` 降級為待核可的發現；非虛構完全不適用 |
| `operation-manual.md` §13 刪除無源裝飾細節，與 sepia 要求加入具體感官細節牴觸 | 依場景切分：非虛構 shuorenhua 勝，小說 sepia 勝。這一條**不需要改動 `style-pass.md`** —— `operation-manual.md` §13 本來就對小說開了豁免，而 `professional-pass.md` 的「絕不杜撰，缺了就問」本來就管住非虛構那一側，兩邊接起來剛好閉合。衝突在措辭不在意圖，sepia 自己的硬性規定就是「不得杜撰具體資訊」 |
| sepia 的節奏修復要求併句拆句與段落參差，與 `bounded` / `in-place` 禁止併句牴觸 | shuorenhua 勝，節奏修復是結構編輯，必須受 scope 管轄。寫出降級梯：`structural` 自由做，`bounded` 只做句內、段落節奏只回報，`in-place` 全部只回報。sepia 的參差目標保留為目標 |
| Tier 計數與 30 項 rubric 兩套評分都想決定改寫深度 | 分治。Tier 管雙語的詞彙與結構命中，成為兩種語言共用的密度機制；rubric 管小說敘事架構並保留其禁止加總條款。硬邊界：rubric 的觀察不得被計數用來決定改寫深度 |

另外，sepia 原本「slop 會累積、群聚了就重寫」的定性說法，替換為 shuorenhua 的數值門檻。這不是衝突，是升級：sepia 的英文檢查因此有了可重現的觸發點。

## 證據紀律

兩個上游的證據紀律都保留，合併沒有放寬任何一邊：

- sepia 的釘選來源帳本（`research/sources.md`）與「實測的關聯不驗證本 skill 的處方」邊界聲明
- shuorenhua 的 L0–L3 分層評測與發布門檻（`evals/benchmark-tiers.md`），含防放水條款：分層判據先於跑分定稿，不得在實跑結果出來後為達標移動層級

**新增一條：所有跨語言的延伸都是設計推論，不是實測結果。** 兩個上游都沒有中文的測量基線。中文小說表面層、中文專業場景包、中文零主語規則、ZH→EN 翻譯腔清單、語言邊界規則 —— 這些各檔案自己標明信心等級，不得在報告裡寫成實測。

## 追上游更新

合併後不能直接 `git pull`。上游若有更新，要手動比對：

```bash
git clone --depth 1 https://github.com/MrGeDiao/shuorenhua.git
git clone --depth 1 https://github.com/allenloves/de-ai-tone.git
git clone --depth 1 https://github.com/Nanako0129/sepia.git
```

de-ai-tone 是單檔，比對 `SKILL.md` 即可。shuorenhua 更新後需重跑簡繁轉換，並重新套用上面 shuorenhua「改動過的」表列的四項編輯。

**sepia 更新後需重新套用上面 sepia「改動過的」表列的全部五項編輯。** 不要只挑其中幾項 —— `discourse-pass.md` 與 `fiction/rubric.md` 的 SCOPE 聲明是 `SKILL.md` 第 9 節據以成立的跨語言證據護欄，`discourse-pass.md` §1／§2 的 operation gate 則是保真合同在非虛構那一側的唯一防線。漏掉任何一項，更新完的 skill 會恢復成「跑事故檢討時指示捏造一條發現」的狀態。

任何一邊的更新都不得覆寫本次新寫的六份檔案（見上表）。
