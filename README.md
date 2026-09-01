# be-human

雙語（臺灣繁體中文與英文）去 AI 味寫作 skill。涵蓋小說與專業文體，以保真為底線。

A bilingual (Taiwan Traditional Chinese + English) de-AI writing skill, covering fiction and professional prose, with fidelity as the floor.

---

## 這是什麼

把文字從「像模型在表演寫作」拉回「像具體人在當前場景下表達」。它不是敏感詞替換器，也不是反技術、反抽象、反專業。

它由三個上游合併而成，分工是刻意的：**保真與力度控制的機制來自 shuorenhua，臺灣用語與標點層來自 de-ai-tone，文體與敘事的診斷內容來自 sepia。** 控制平面本來就不重疊 —— 一個回答「我可以動到什麼程度、什麼絕不能碰」，另一個回答「這種文體需要什麼」，第三個管的是語域正確性。合併不是二選一。

## 和單獨使用任一上游的差別

| | shuorenhua | sepia | be-human |
|---|---|---|---|
| 臺灣用語與標點（always-on） | 有 | 無 | 有 |
| 力度檔位、刪除授權、長度護欄 | 有 | 無 | 有 |
| 保真回讀與量化回退門檻 | 有 | 無 | 有 |
| 小說敘事架構（StoryScope） | 無 | 有 | 有 |
| 中文小說的句子層 | 無 | 無（英文詞彙） | **新增** |
| 專業場景包 | 6 個（中文） | 5 個（英文） | 10 個：5 個雙語、4 個結構語言中性、1 個中文 |
| 中英混排的語言路由 | 無 | 無 | **新增** |
| 雙向翻譯腔（EN↔ZH） | 單向 | 無 | **新增** |
| 安全邊界（文字即不可信資料） | 無 | 有 | 有 |

## 架構

三層，順序不能反：

- **第 0 層｜語言路由閘門** —— 任何掃描開始前先按母體語言切段。中文段跑中文詞表，英文段跑英文詞表。中文句子裡的英文術語是 protected span，不是英文禁用表的候選。沒有這一層，下游每條規則都會在中英混排的技術文字上誤觸。
- **第 1 層｜臺灣繁體語域** —— 只要輸出含繁體中文就生效，不需要使用者要求。優先於其餘所有規則，不受 scope 或力度豁免，也不佔用風格動作預算 —— 修支語是正確性，不是風格選擇。
- **第 2 層｜去 AI 味框架** —— 使用者要求時啟用。

路由是**兩條軸**：場景（`chat` / `status` / `docs` / `public-writing` / `fiction`）決定力度與刪除授權；場景包（README、release-note、forum-post、issue-reply、api-reference、faq、postmortem、ticket、tech-article）決定這種文體需要什麼，且不覆蓋 protected spans、Tier、檔位與回讀。

操作是**使用者看到的動詞**，力度與 scope 是底下的參數：

| 操作 | 預設參數 |
|---|---|
| `write` | 依場景 |
| `review`（只標問題，不改） | annotation mode |
| `refactor`（最小幅度原地修改） | `standard` + `bounded` |
| `recreate`（完全重寫） | `aggressive` + `structural` |

`recreate` 在 `in-place` scope 下不可用，除非使用者明確提高 scope。

## 怎麼用

安裝後直接說需求即可，例如：

- 「這段太像 AI，幫我改一下」
- 「先別改，先標問題」→ 進 annotation mode，只輸出 1–5 個病灶
- 「一句都別刪」→ 進 `in-place`，只做句內降調
- 「這篇技術文章要發布，幫我看一下」→ 命中 `tech-article` 場景包
- 「humanize this release note」→ 走英文側
- 「這篇短篇小說讀起來很假」→ 進 `fiction`，跑敘事架構與（中文的話）中文小說表面層

## 安裝

複製整個目錄到 skills 目錄底下：

```bash
cp -r be-human-v1 ~/.claude/skills/
```

Windows（PowerShell）：

```powershell
Copy-Item -Recurse be-human-v1 "$env:USERPROFILE\.claude\skills\"
```

新 skill 在執行中的工作階段立即生效，不必重開。

## 證據邊界

兩個上游的證據紀律都保留，合併沒有放寬任何一邊。

- **實測的**：StoryScope 的敘事特徵分佈、編輯動作比例 74/18/8、專家偵測者研究、slop 分類法（全部為**英文語料**）；shuorenhua 的連接詞密度校準（95 條語料）與長文縮水區間（−18% 至 −39%）。來源帳本見 `research/sources.md`。
- **發布門檻**：L1 硬約束失敗數必須為 0，誤殺率 < 10%，且分層判據先於跑分定稿。見 `evals/benchmark-tiers.md`。
- **推論的**：**所有跨語言的延伸。** 中文小說表面層、中文專業場景包、中文零主語規則、ZH→EN 翻譯腔清單、語言邊界規則 —— 兩個上游都沒有中文的測量基線，這些是有根據的設計推論，不是實測結果。各檔案自己標明信心等級。

不要在報告裡把推論寫成實測，也不要對中文文字給出模型歸因。

## 授權

**CC BY-SA 4.0**（整體）。

de-ai-tone 以 CC BY-SA 4.0 授權，其 share-alike 條款擴散到整份合併作品。MIT 可以被再授權為 CC BY-SA，反向不成立，所以三方合流的唯一合法出口就是 CC BY-SA 4.0。

散布時須具名三位原作者並保留四份 LICENSE 檔：

| 上游 | 作者 | 授權 |
|---|---|---|
| [shuorenhua](https://github.com/MrGeDiao/shuorenhua) v2.3.1 | MrGeDiao | MIT |
| [de-ai-tone](https://github.com/allenloves/de-ai-tone) `495a7f0` | allenloves | CC BY-SA 4.0 |
| [sepia](https://github.com/Nanako0129/sepia) v0.4.0 | Nanako Tsai | MIT |

完整的逐檔出處對照、四件規則衝突的處理紀錄，以及追上游更新的方法，見 [`ATTRIBUTION.md`](./ATTRIBUTION.md)。
