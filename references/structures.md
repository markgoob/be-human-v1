# 結構反模式

> 本檔案是解釋、示例與操作細則；行為合同的單源是 `SKILL.md`，兩處表述不一致時以 `SKILL.md` 為準。

> 這裡管的是句子、段落與版面層面的痕跡，不是單詞。詞表在 [`phrases-zh.md`](./phrases-zh.md)（中文）與 [`style-pass.md`](./style-pass.md) §3（英文）；那兩份負責「哪些詞」，本檔負責「怎麼動結構」。

> 下面各條的 `預設動作` 都是 `structural` scope 下的動作，實際執行時按 edit scope 降級：`bounded` 不併句、不重排，段落層面的動作只回報不執行；`in-place` 不刪句子、不動句子與段落邊界，全部只回報。個別條目另有明列的降級表時（第 18、34 條），以該表為準。

## 標記說明

每條標題後面標語言範圍：

- `[ZH]`　只在中文母體段判。套到英文段落會誤傷，通常方向還相反。
- `[EN]`　只在英文母體段判。中文母體段裡夾帶的英文是術語或 protected span，永遠不是候選。
- `[both]`　兩種母體段都判，計數口徑各按各的（中文按字數、英文按詞數）。
- `[structural]`　管版面、標記與位置，與語言無關；個別子項只在英文成立時會另外標。

信心標記：

- `grounded`　上游有明列的量測（語料規模、統計值或實測比例），且量測語言與本條適用語言一致。
- `inference`　跨語言、跨場景或跨文體的合理外推，沒有量測。**所有把英文量測搬進中文的條目一律是 inference**：兩個上游都沒有中文的通用量測基線。
- `speculative`　合併期新訂、還沒有任何驗證的判準。

編號沿用 shuorenhua 的 1–26，沒有重排；27 起是合併新增。

## 規則索引

| # | 規則 | 範圍 | 信心 |
|---|---|---|---|
| 1 | 二元對比假戲劇 | both | 現象 grounded／閾值 inference |
| 2 | 否定式列舉 | both | inference |
| 3 | 戲劇化碎句 | both | inference |
| 4 | 反問式鋪墊 | both | inference |
| 5 | 虛假主語 | both | inference |
| 6 | 被動語態堆砌 | both | 英文 grounded／中文 inference |
| 7 | 三件套列舉 | both | grounded（英文）／中文 inference |
| 8 | 「首先…其次…最後」機械排列 | ZH | inference |
| 9 | Wh- 開頭句 | EN | grounded |
| 10 | 總結式收尾 | both | grounded（英文）／中文 inference |
| 11 | 對稱填充 | ZH | inference |
| 12 | 無源引用 | both | inference |
| 13 | 加粗濫用 | structural | inference |
| 14 | 分條列點強迫症 | structural | inference |
| 15 | 正能量收尾強迫症 | both | grounded（英文）／中文 inference |
| 16 | 假口語化／硬凹網感 | ZH | inference |
| 17 | 除錯腔敘事 | both | inference |
| 18 | 節奏單調 | both | 見條內 |
| 19 | 價值拔高骨架 | ZH | inference |
| 20 | 標點腔（破折號過密） | ZH | 見條內 |
| 21 | 動詞名詞化 | both | 英文 grounded／中文 inference |
| 22 | 同義詞躲避 | both | inference |
| 23 | 連詞過密 | ZH（限 `public-writing`） | grounded |
| 24 | 裝飾性細節 | both | inference |
| 25 | 借喻場混用 | both | 中文 inference／英文 inference |
| 26 | 版面裝飾強迫症 | structural（門檻按中文字數） | inference |
| 27 | Participial clauses | EN | 見條內 |
| 28 | Abstract-noun-of-noun wrappers | EN | grounded |
| 29 | Unclear pronouns | EN | grounded |
| 30 | Run-on and tangled sentences | EN | grounded |
| 31 | 「Seem to + verb」 | EN | grounded |
| 32 | Filter words | EN | 社群語料／專業豁免 inference |
| 33 | 版面與標記痕跡 | structural（`Title Case` 子項 EN） | 見條內 |
| 34 | 版面位置痕跡 | structural | 見條內 |

## 修復順序

專業編輯真的動手的頻率順序（LAMP-2025：18 位 MFA 寫作者改 1,057 段 LLM 文字，**英文語料實測**）：

| 序 | 病灶 | 佔比 | 本檔對應 |
|---|---|---|---|
| 1 | 用詞不當 | 28% | 第 21、22、29、31 條；詞表見 `style-pass.md` §3 |
| 2 | 句構鬆散 | 20% | 第 30 條（英文長句）、第 18 條（節奏） |
| 3 | 冗餘鋪陳 | 18% | 第 10、15、27 條 |
| 4 | 陳腔 | 17% | 第 25 條。替換必須換成場景專屬的說法，**不能換成更平淡的改述**——那是實測到的機器失敗模式 |

該研究另外三項（具體度不足、purple prose、時態不一致）沒有排序，處理方式見 `style-pass.md` §1。

**中文段落把這個順序當建議，不當門檻（inference）。** 量測語料是英文，中文沒有對應基線。它的用途是「時間或預算不夠時先修哪個」，不是「修完前一項才准修下一項」。

## 1. 二元對比假戲劇 `[both]`

**模式**：先否定 X，再肯定 Y，製造虛假的頓悟感。

```
❌ 這不是技術問題，而是管理問題。
❌ It's not about the code. It's about the culture.
```

```
✅ 管理流程比程式碼本身更容易出問題。
✅ The culture around code review matters more than the code itself.
```

**檢測**：看密度和分佈，不看單次出現。**先按下面「保留條件」把豁免項剔除，再對剩下的計數**——豁免項不計入密度，也不因為密度超標被改；只有剩餘項超標才處理。這樣改完的輸出重新過一遍規則不會再次命中。命中訊號：

- 同段連續 2 組以上（含與價值拔高骨架混合疊加）
- 全文按長度歸一（計數口徑同 [嚴重度分級](./severity.md)：中文按字數，英文按詞數，程式碼片段 / 路徑 / 命令 / 版本號各計 1，標點和空白不計）：< 300 字/詞 出現 2 處以上；300–1000 字/詞 出現 3 處以上；> 1000 字/詞 平均每 300 字/詞 1 處以上
- 變體同樣計入：`不像 A，像 B`、`要的是 X，不是 Y`、`X 不行，Y 才行`，以及連續多條以否定收尾的列表項或表格行
- 跨句變體和換字變體一樣計入：`不是 A。而是 B`（句號斷開）、`與其說 A，毋寧說 B`、`你以為 A，其實 B`、`我一直以為 A，後來才發現 B`、`回頭才發現`、`大家都說 A，可真相是 B`、`答案恰恰相反`、`真正值錢的從來都與 A 無關`。這裡管的是「先立一個讀者並沒有的誤解，再推翻它抬價」這個動作，換任何字面都算；**判據和豁免口徑不變**，仍按本條的密度閾值和豁免上限處理，不因為變體多就升級成一刀切
- 英文母體段的同型骨架一併計入：`It's not X, it's Y`、`not only X but also Y`、`X isn't just A — it's B`、`This isn't about A. It's about B.`
- 讀到後面能預判下一句形狀

**預設動作**：豁免項原樣保留；剩餘超標的骨架按 `in-place` 替代動作換成中性連線或直接陳述（`X 不夠，Y 更重要`、`相比 X，Y 更能說明問題`），兩邊資訊都要保留。只把 `不是 X，是 Y` 倒裝成 `Y，不是 X` 不算完成降密度——骨架還在。英文段落的替代動作更直接：**say the one thing you mean**——只講你真正要講的那一件事，不要保留骨架再換連接詞。不要見一個殺一個，也不要把豁免項一起抹平成同一種平鋪句。

**保留條件**：豁免上限 2 處。超過 2 處都聲稱「承擔論證」時不再逐條豁免——每一處都說得出理由，恰恰是骨架依賴的表現，仍按密度處理。逐條判據：

- **術語定義**（最多 1 處，通常在首句或定位句）：`X 不是 A，是 B` 用來糾正讀者對 X 是什麼的誤讀
- **論證骨架**（最多 1 處）：前半句是讀者會真實持有的誤解，且刪掉它之後，後文的資料、結論或動作會失去依據——「讀起來氣勢弱一點」不算
- **引用原文、被討論物件**：不計入密度，也不受上述數量上限約束

SF-40 那類「作者刻意用對比結構承載全文論點」屬於用例級例外，判據和理由記在 [benchmark-tiers.md](../evals/benchmark-tiers.md) 的例外表，不作為通用豁免口。

**信心**：現象 grounded（RUSSELL-DETECT-2025 的 15 類線索裡，Sentence Structure 提及率 35.9%，明列 `it's not just X it's Y`；英文非虛構 300 篇）。密度閾值與豁免上限 inference——沿用 shuorenhua 的既有校準，上游未標明該校準的量測語料，本合併未重測。

## 2. 否定式列舉 `[both]`

**模式**：先說不是什麼，再說是什麼。繞了一圈。

```
❌ 它不是框架，不是庫，也不是工具——它是一種思維方式。
❌ It's not a framework. It's not a library. It's a way of thinking.
```

```
✅ 把它當作一種思維方式，不是一個具體工具。
✅ Think of it as a mental model, not a tool.
```

## 3. 戲劇化碎句 `[both]`

**模式**：用句子碎片製造假的力量感。

```
❌ 三年。兩個人。一個想法。
❌ Three years. Two people. One idea.
```

```
✅ 兩個人花了三年把這個想法做成了產品。
✅ Two people spent three years turning the idea into a product.
```

## 4. 反問式鋪墊 `[both]`

**模式**：用反問或「如果」開頭吊胃口。

```
❌ 如果我告訴你，90% 的新創公司都在犯同一個錯誤呢？
❌ What if I told you 90% of startups make the same mistake?
```

```
✅ 90% 的新創公司在定價上犯同一個錯誤：按成本定價而不是按價值定價。
✅ 90% of startups misprice their product, using cost-based pricing instead of value-based.
```

## 5. 虛假主語（False Agency）`[both]`

**模式**：給無生命的事物安上人類動作（「賦能」「助力」「驅動」）。當句子抽象空泛、沒有具體資訊時優先改寫。技術文件中描述系統行為的非人主語（「閘道器返回 504」「快取過期」）是合理的，不需要改。

```
❌ 該框架賦能了開發者社群。
❌ The framework empowers the developer community.
```

```
✅ 開發者用這個框架能少寫 30% 的樣板程式碼。
✅ Developers write 30% less boilerplate with this framework.
✅ 閘道器在超時後返回 504。（技術描述，不改）
```

## 6. 被動語態堆砌 `[both]`

**模式**：連續使用被動語態，隱藏動作執行者。研究論文、實驗報告或正式學術摘要裡的常規被動不一定要改。

```
❌ 系統被最佳化後，效能被顯著提升，使用者體驗被大幅改善。
❌ The system was optimized, performance was improved, and user experience was enhanced.
```

```
✅ 我們最佳化了資料庫查詢，頁面載入從 3 秒降到 0.8 秒。
✅ We optimized database queries and cut page load time from 3s to 0.8s.
```

```
✅ The experiment was conducted by researchers at MIT.（學術語體，可保留）
```

英文段落的「過量被動」屬於 LAMP-2025 第一類（用詞不當，28%）的修法之一，與第 29 條的代詞不清同批處理。

## 7. 三件套列舉 `[both]`

**模式**：AI 偏愛三個一組。兩個或一個往往更自然。

```
❌ 創新、協作、卓越。
❌ Innovation, collaboration, and excellence.
```

```
✅ 把東西做出來，做好。
✅ Build things. Build them well.
```

**預設動作**：改成兩項或四項，把節奏打斷；或直接刪到只剩真正有內容的那一項。英文段落同樣處理三個並列形容詞、三個並列子句、三個並列意象。

**與第 34 條的分工**：本條管**句內**的三件套；整份文件到處都是「剛好三項」的清單是版面位置痕跡，歸第 34 條。

**信心**：grounded（RUSSELL-DETECT-2025 的 Sentence Structure 類別明列「固定三項列舉」，英文非虛構）。中文適用性 inference。

## 8. 「首先…其次…最後…」機械排列 `[ZH]`

**模式**：中文特有的機械遞進，製造假的邏輯感。

```
❌ 首先，我們需要明確目標；其次，制定計畫；最後，執行落地。
```

```
✅ 先把目標定清楚，然後排優先順序，邊做邊調。
```

## 9. Wh- 開頭句 `[EN]`

**模式**：用 What/When/Where/Which/Who/Why/How 開頭的句子在 AI 文字中過度集中。

```
❌ What makes this approach unique is its simplicity.
```

```
✅ This approach works because it's simple.
```

## 10. 總結式收尾 `[both]`

**模式**：每段或全文末尾用「總之」「綜上」做總結，重複已說過的內容。

```
❌ 綜上所述，該方案在效能、安全性和可維護性方面都表現優異。
❌ In conclusion, this approach excels in performance, security, and maintainability.
```

```
✅ 刪掉。前面說清楚了就不用再說一遍。
✅ Delete it. If you said it clearly above, don't repeat it.
```

## 11. 對稱填充（Symmetry Padding）`[ZH]`

**模式**：為了「平衡」而硬湊對仗，沒有資訊增量。

```
❌ 既要保證速度，又要保證品質；既要創新突破，又要穩定可靠。
```

```
✅ 速度和品質之間我們優先品質。
```

英文的對應病灶不是對仗，是成對抽象名詞（`desperation and resolve`），歸第 28 條。

## 12. 無源引用 `[both]`

**模式**：用「研究表明」「資料顯示」「專家指出」但不給具體來源，製造假的權威感。

```
❌ 研究表明，遠端辦公能提高 30% 的生產力。
❌ Studies show that remote work increases productivity by 30%.
```

```
✅ Stanford 2023 年的一項實驗發現，全遠端員工的程式碼提交量比混合辦公多 13%。
✅ A 2023 Stanford experiment found fully remote employees committed 13% more code than hybrid workers.
```

補來源只能用原文或使用者已有的資訊。找不到來源時刪掉整句或標成待確認，**不得生成一個看起來合理的出處**。

## 13. 加粗濫用 `[structural]`

**模式**：機械地給每個要點加粗，製造假的層次感。

```
❌ **使用者體驗：** 介面全面升級。**效能最佳化：** 演算法顯著提升。**安全加固：** 新增端到端加密。
```

```
✅ 介面重新設計了，演算法快了 2 倍，加了端到端加密。
```

## 14. 分條列點強迫症 `[structural]`

**模式**：任何內容都要 1. 2. 3. 分條，連簡單回覆也列點，製造假的條理感。

```
❌ 關於這個問題，我的建議如下：
   1. 先檢查配置檔案
   2. 確認環境變數
   3. 重啟服務
```

```
✅ 配置檔案裡的 DB_HOST 可能寫錯了，先看一眼。不是的話重啟一下服務試試。
```

## 15. 正能量收尾強迫症 `[both]`

**模式**：不管前面說了什麼，最後一段必須上價值、給雞湯、展望未來。

```
❌ ……總之，讓我們擁抱變化，積極迎接 AI 時代的無限可能！未來可期！
❌ We'll keep iterating and continue to improve the experience for everyone.
```

```
✅ 刪掉。前面說完了就結束。
```

## 16. 假口語化／硬凹網感 `[ZH]`

**模式**：AI 試圖「接地氣」時硬塞網路流行語（絕絕子、誰懂啊、真的會謝），反而更假。真人用這些詞是隨機的，AI 是批次的。

```
❌ 姐妹們！這個工具真的絕絕子！誰懂啊，效率直接拉滿！狠狠心動了！
```

```
✅ 這個工具確實好用，主要是批次處理的速度快，省了不少時間。
```

## 17. 除錯腔敘事 `[both]`

**模式**：AI 在程式設計場景中用 postmortem / SRE 口吻講日常事務——「兜住」「落盤」「根因」「收口」。把 debug 術語泛化到一切對話中。

```
❌ 我已經把差異收窄了，根因基本坐實，接下來做一個更硬的排除法把問題打掉。
```

```
✅ 原因找到了：是快取過期導致的。我把可能性排查了一遍，現在就剩這一個。
```

英文母體段的同型病灶是把 `mitigate`、`root-cause`（當動詞）、`circle back`、`bandwidth` 搬進日常回覆。判準一樣：**場景是不是真的在做事故處理**。（inference：兩個上游都沒有這一類的量測。）

## 18. 節奏單調（統計訊號）`[both]`

**模式**：AI 文字的節奏比人類均勻得多。兩個子訊號：

- **句長均勻**：每句話長度幾乎一樣（句長標準差約 1.2，人類約 4.7+）。表現為「讀起來很平，沒有呼吸感」。
- **句式骨架重複**：同一種句法形狀反覆出現，最常見的是二元對比（`不是 X，是 Y`），其次是每一節末尾都落一個對仗短句。單句都成立，連著讀能預判下一句形狀。

**檢測**：不是看單個詞，而是看整段乃至全文的節奏。長短句應該交替出現；同型骨架的密度閾值見第 1 條。

**預設動作**：句長層面合併或拆分句子，製造長短交替；骨架層面按第 1 條先剔除豁免項，再改剩餘超標的那幾處。兩個層面都不重寫全文。

**預設動作按 edit scope 降級**：

| scope | 能做到哪 |
|---|---|
| `structural` | 自由合併、拆分、重新分段。直接做出長短交替；骨架層面按第 1 條剔除豁免項後，改剩餘超標的那幾處 |
| `bounded` | 只做句內拆分與刪子句。句長層面的合併句子、段落節奏調整**一律只回報不執行**，寫在刪除清單旁的觀察欄，由使用者拍板 |
| `in-place` | 全部只回報，不動任何句子邊界 |

**回讀**：第 27、30 條的拆句動作會製造一串長度相近的短句。拆完回頭重數一次句長序列，否則等於用第 30 條的修法生出第 18 條的病。

**信心**：句長標準差 1.2 / 4.7+ 是上游列出的量測值，但上游未標明語料語言；套在中文段落上按 inference 處理，套在英文段落上與 RUSSELL-DETECT-2025「人類句長變化大」的觀察方向一致。

## 19. 價值拔高骨架 `[ZH]`

**模式**：先給一個事實，再用 `不僅僅是……更是……`、`真正的 X 不是……而是……`、`最後比拼的是……` 把句子抬高成「洞見」。

```
❌ 這不僅僅是一個產品，更是一種信念的傳承。
❌ 真正的競爭力不是功能堆砌，而是體驗細節。最後比拼的是執行效率。
```

```
✅ 這就是一個產品判斷：體驗細節決定它能不能長期被用下去。
✅ 產品做得再多，最後還是看體驗細節和執行效率。
```

英文的 `not only X but also Y`、`it's not just X, it's Y` 屬於同一個動作，但計數併入第 1 條，不重複計。

## 20. 標點腔（破折號過密）`[ZH]`

**模式**：把英文 em-dash 的使用習慣帶進中文——首句就用破折號起手，一段裡連續多個 `——`，插入、轉折、補充全靠破折號承接；常伴隨分號連用、頓號亂燉和中英混排下的標點崩壞。跨模型現象，提示詞往往壓不住。

**檢測**：看密度和位置，不看單次出現。計數單位是**插入處**，不是破折號符號：一對 `——插入內容——` 計一處，單個 `——` 承擔轉折或補充也計一處。命中訊號：首句破折號起手、單段兩處以上插入、連續多段都靠破折號承接。單個破折號不是問題，不要見一個殺一個。

```
❌ 這個工具最打動我的是速度——開啟就是結果。搜尋、啟動、剪貼簿——所有操作都在一個輸入框裡——你甚至不用記快捷鍵。
```

```
✅ 這個工具最打動我的是速度：開啟就是結果。搜尋、啟動、剪貼簿，所有操作都在一個輸入框裡，你甚至不用記快捷鍵。
```

```
✅ 配置支援環境變數覆蓋——容器部署時不用改檔案——其餘場景直接編輯 `config.toml`。
```

最後一例只有**一處**成對插入（兩個 `——` 符號構成一處），不命中密度訊號，放行。

**預設動作**：多餘的破折號按語義改回冒號、逗號、括號或直接斷句；一段最多保留一處真正承擔插入或遞進的。

**保留條件**：標題和命名裡的連線符（`todo — 終端待辦`）；引用原文；破折號本身是討論物件；全段僅一處且確實承擔插入語氣。

**改成冒號時的限制**：本條的預設動作允許把多餘的破折號改成冒號，但冒號本身受 [`punctuation.md`](./punctuation.md) 第 2 節約束——只有列舉、引文、定義三種用法才能用冒號。上面第二個 ✅ 範例的冒號屬於「引出列舉」，成立；若只是承接說明，改逗號或直接斷句。把破折號的毛病轉嫁給冒號，只是換個符號生同一種病。

**英文段落不套本條。** 方向相反：RUSSELL-DETECT-2025 的 Grammar & Punctuation 類（提及率 24.8%）記錄的英文機器特徵是**迴避** dash 與省略號，人類反而混用 dash、括號與短逗號段。英文的 em-dash 按 `style-pass.md` §7 的白名單處理——單一個 em-dash 不是證據。把中文的破折號密度規則搬進英文段落，會把英文改得更像機器。

**信心**：中文密度判準 inference（沿用 shuorenhua，未標明量測）；英文的反向觀察 grounded（英文非虛構 300 篇）。

## 21. 動詞名詞化 `[both]`

**模式**：把動作壓成「空動詞 + 抽象名詞」。句子變長，資訊沒變。`進行 / 實現 / 完成 / 開展 / 起到 / 具有` 後面跟一個動名詞是典型訊號。

```
❌ 我們對流程進行了最佳化，實現了效率的顯著提升。
❌ 完成了對監控體系的梳理，起到了很好的支撐作用。
❌ The team performed an optimization of the deployment workflow.
```

```
✅ 我們把流程改順了，一個人一天能多處理 20 單。
✅ 梳理了監控，現在報警能定位到具體服務。
✅ The team simplified the deployment workflow.
```

**檢測**：`進行了 X` / `實現了 X 的 Y` / `完成了對 X 的 Y` / `起到了 X 的作用` / `具有 X 的意義` / `開展 X 工作`。英文對應 `perform an analysis of`、`conduct a review of`、`achieve an improvement in`，以及 `realization / determination / transformation` 這類抽象名詞當主語（英文實測約為人類的 2 倍，LAMP-2025 與 REINHART-STYLE-2025）。shuorenhua 的校準腳本 `hard_metrics.py --residual` 會報數（只報數不判死；該腳本未隨本 skill 併入，這裡只當出處記錄）。

**預設動作**：還原成直接的動詞。還原後如果發現原句其實沒說清誰做了什麼，按「清理後的落點」合同處理，允許變短並標註缺口徑，不補事實。

**保留條件**：法律、契約、公文、正式公告裡的固定表述（`進行公示`、`予以受理`）；`docs` 裡已經是穩定術語的名詞化（`增量編譯`、`執行計畫生成`）；使用者明確要求正式語體的對外材料。

**與第 28 條的邊界**：本條抓的是「空動詞 + 動名詞」；第 28 條抓的是「抽象名詞包名詞」（`an optimization of the workflow` 裡的 `of` 結構）。同一句可能兩條都命中，各修各的，不要重複計密度。

## 22. 同義詞躲避 `[both]`

**模式**：同一個東西在相鄰幾句裡被迫換三種說法，而且一次比一次抽象。人寫東西不怕重複關鍵詞，模型第二次就換近義詞、第三次再換一個，讀起來發油。

```
❌ 他開始學修表。這門手藝上手比想像中慢，練了半年才敢接活。後來這項技能成了他主要的收入來源。
❌ The team shipped the parser. This component handles 4MB files. The module now runs in CI.
```

```
✅ 他開始學修表。修表上手比想像中慢，練了半年才敢接活。後來修表成了他主要的收入來源。
✅ The team shipped the parser. It handles 4MB files and now runs in CI.
```

**檢測**：同一指稱物件在相鄰 2–3 句裡換了 2 次以上說法，且換法是往上升格（`修表 → 這門手藝 → 這項技能`、`parser → component → module`）。代詞（`它`、`這個`）不算——正常照應本來就該用代詞。

**預設動作**：統一回最具體的那個說法，其餘改成原詞或代詞。

**保留條件**：換的說法帶來新資訊或新限定（`修表 → 上門修表`）；兩個說法指的其實不是同一個物件；術語與口語的對照本身就是文字在做的事（`索引 / index`）；引用原文。

**注意**：這一條同時約束改寫動作本身。清理 [嚴重度分級](./severity.md) Tier 3 的高密度詞時，不要用同義詞輪換降密度——那會把密度問題換成這裡的油滑感。第 29 條把代詞還原成名詞時也受本條管：**還原成原文用過的那個詞**，不要順手升格。

## 23. 連詞過密 `[ZH，限 public-writing]`

**模式**：`因為 / 所以 / 但是 / 同時 / 此外 / 然而 / 因此` 幾乎每兩句出現一個，條件連詞 `如果 / 否則` 同屬此類。中文小句靠語序和事理就能相接，連詞堆砌是英文式顯性銜接的搬運。

```
❌ 因為店裡生意不好，所以他決定把下午的時間用來學修表，同時也能多一門手藝。
```

```
✅ 店裡生意不好，他下午閒著，就學起了修表，多一門手藝總沒壞處。
```

**檢測**：**只在 `public-writing` 的敘事、觀點、隨筆類文字上判，`docs` / `status` / `code-context` 不判。** 這一條沒有全域性密度閾值，原因是實測資料直接否掉了全域性判據。shuorenhua 的 `hard_metrics.py --calibrate` 在 95 條語料上跑出：SNF（不該改）連詞密度中位 5.26 / 千字，高於 SF（該改）的 0.00；**SNF 的最高值 81.08 還高於 SF 的最高值 80.00**。最硬的證據是 benchmark 裡的一對同密度用例——SF-50（`public-writing` 敘事）80.00 / 千字該刪一半，SNF-39（`docs` 遷移說明）81.08 / 千字一個都不能刪。技術文字靠 `如果…否則`、`因為…所以` 承擔條件和因果，按密度一刀切會優先誤傷它們。

在適用場景內看分佈，不看總量：連續三句每句都以連詞開頭，或同一個連詞在一段裡出現 3 次以上。

**預設動作**：刪掉一半，讀得斷的地方不補回來。刪完通讀一遍，事理接不上的地方再放回最必要的那個。

**保留條件**：連詞真的在承擔轉折、讓步或因果，刪掉會讀錯；`docs` 裡的條件說明和步驟銜接；法律與規範文字；`status` 裡的時間線因果。

**不得外推到英文段落。** 英文靠顯性連接詞承擔銜接，而 `style-pass.md` §4 記錄的方向剛好相反：模型的 `because` 用量只有人類的兩成，屬於**要加回來**的項。把本條套進英文只會加重那個缺口。

**信心**：grounded（95 條語料的校準與同密度反例，中文 benchmark）。場景限制是校準結論的一部分，不是保守設定，不得放寬。

## 24. 裝飾性細節 `[both]`

**模式**：用具體的時間、天氣、動作、物件偽造現場感。這些細節沒有來源，也不改變後文任何判斷，只負責讓畫面顯得真實。假細節越具體，AI 味越重。

```
❌ 凌晨三點，辦公室只剩他一個人。窗外下著雨，桌上的咖啡早就涼了。他點了第三根菸，盯著螢幕上那行報錯。
```

```
✅ 那個 bug 卡了他兩天。最後發現是時區配置在容器裡沒生效，本地怎麼測都測不出來。
```

**檢測**：兩條同時成立才算命中——細節**沒有來源**（不是使用者提供的、不是可核驗的），並且**刪掉後文不變**（事實、判斷、因果都不受影響）。只滿足一條不算。這一條和第 16 條「假口語化」不同：那條抓的是硬塞網路流行語，這條抓的是偽造的生活細節。

**預設動作**：刪掉。刪完段落如果沒了落點，用原文已有的資訊重組，不補新細節。

**保留條件**：使用者自己提供的經歷細節，哪怕瑣碎也保留；細節確實改變後文（`那天是週日，維修點沒開門`）；虛構、小說、劇本裡屬於人物視角和行動的細節；`docs` 裡的復現條件、環境說明和時間戳。

## 25. 借喻場混用 `[both]`

**模式**：同一段裡從多套不相干的比喻系統藉詞。常見七套：道路競賽、戰爭攻防、建築災害、溫度、倉儲、海洋航行、機器器官。單獨一套用得準沒問題，多套混在一起說明在用比喻替代說明。

```
❌ 這個賽道的護城河正在坍塌，團隊需要重新點燃引擎，才能在這波浪潮裡活下來。
❌ We need to unlock runway, harden the moat, and keep the engine warm through this wave.
```

```
✅ 這個方向的門檻在降低，去年還得自研的部分現在有開源方案了。團隊得找新的差異點。
```

**檢測**：短距離內（約 800 字／詞視窗）命中 3 套以上借喻場。`hard_metrics.py --residual` 會統計，並已排除字面用法（`搜尋引擎`、`程式碼倉庫`、`商品庫存` 不計；該腳本未隨本 skill 併入）。

**預設動作**：先全部還原成本義。還原後意思已經清楚的，一個比喻也不用放回。**不要換成更平淡的改述**——陳腔的正確修法是換成場景專屬的說法，或整句刪掉（LAMP-2025 記錄的機器失敗模式就是改述成更平淡的版本）。

**保留條件**：所寫物件本身就是這些東西（真的在講倉庫、溫度、船）；行業穩定術語（金融的 `槓桿`、投資語境的 `護城河`）；使用者明確要求的修辭風格；小說、詩歌和抒情寫作按意象是否屬於同一套感受判斷，不按數量機械刪。

**信心**：七套借喻場的分類與 3 套門檻沿用 shuorenhua（未標明量測，inference）；英文段落套同一套分類是跨語言外推（inference）。

## 26. 版面裝飾強迫症 `[structural，門檻按中文字數]`

**模式**：用排版元素製造「這篇很用心」的表象。與第 13 條（加粗濫用）和第 14 條（分條列點強迫症）同源，但管的是那兩條沒訂的量化上限，以及裝飾性符號。

**判準**：

- **加粗**：每段至多一處，且只用於讀者掃讀時必須抓住的詞。整句加粗一律禁止。
- **分點列項**：只在內容真正並列且超過三項時使用。兩三個相關的點，寫成一段話。
- **小標題**：千字以內的文章不設小標題。
- **段尾微型總結**：禁止每段結尾都收一句「因此⋯⋯」「這說明⋯⋯」。一篇文章只在真正的結尾總結一次，或者不總結。參見第 10 條。
- **Emoji**：不主動加。標題與列點前的裝飾性 emoji 一律省去。

```
❌ ## 🚀 效能最佳化
   我們做了三件事：
   1. **快取**：加了 Redis
   2. **索引**：補了兩個複合索引
   因此，回應時間顯著下降。✨
```

```
✅ 加了 Redis 快取，補了兩個複合索引，回應時間從 800ms 降到 120ms。
```

**預設動作**：超出上限的加粗還原成一般文字；不足四項的列點併回段落；千字以內的小標題刪除；裝飾性 emoji 刪除；段尾微型總結刪除。

**保留條件**：使用者自己先用 emoji，或明確要求；`scene-packs.md` 裡 README、release note、FAQ 這類本來就靠版面導覽的體裁，小標題與列點按該場景的慣例辦，不受本條上限約束；技術文件中加粗用於標示參數名或警告等級的固定格式。

**適用邊界**：上面的數字門檻按中文字數校準，只在中文母體段生效。英文段落不套這些門檻，改用第 33 條的場地慣例判準。兩條同時可用時，**場地語料優先**——本條的保留條件本來就這樣寫。

## 27. Trailing and leading participial clauses `[EN]`

**Pattern** — a comma plus an `-ing`/`-ed` clause hung off a finite clause. LLM prose uses these at up to 5× the human rate (LAMP-2025, REINHART-STYLE-2025; English corpora).

```
❌ He ducked under the ropes, evading Show's heavy blows.
❌ Stuffing his mouth, Joe ran for the door.
❌ The service returned 504, causing downstream retries to pile up.
```

```
✅ He ducked under the ropes. Show's next blow went wide.
✅ Joe stuffed his mouth and ran for the door.
✅ The service returned 504. Downstream retries piled up.
```

**Signal** — count participial clauses per paragraph, not per document. Leading ones are the louder tell; trailing ones are the more common.

**Default action** — decide by whether the clause carries new information:

- It restates the main clause → **delete it.** This is the redundant-exposition fix (18%): "cast long shadows over the desolate landscape" → "cast a long shadow."
- It carries a real second action or a real causal step → give it its own short sentence with a finite verb, and name the subject.

**Keep when** — fixed connectives (`Speaking of which`, `Given that`, `Assuming no regression`); absolute constructions that the venue's register genuinely uses (academic, legal, spec text); the clause is inside quoted material; the author's verified habit (`style-pass.md` §7).

**Reread** — splitting produces a run of short, similar-length sentences. Re-check rule 18 before you call the paragraph done.

**Confidence** — the 5× overuse is `grounded` (English measurement). The per-paragraph threshold below is `speculative`: neither parent sets one. Working default — not a finding at 1 per paragraph; a finding at 2+ in one paragraph, or when three consecutive paragraphs each open or close with one.

## 28. Abstract-noun-of-noun wrappers `[EN]`

**Pattern** — `a/the [abstract noun] of [noun] (and [noun])`, and `the [adj] [noun] of [possessive]`. These part-of-speech shapes run 2–5× overrepresented in LLM prose and are heavily edited out by professionals (LAMP-2025, REINHART-STYLE-2025).

```
❌ a mix of pride and fear · a sense of wonder · a pang of nostalgia · the weight of expectation
❌ the intricate tapestry of its architecture · the unspoken plea in her voice
❌ Paired abstractions: desperation and resolve · curiosity and caution
```

```
✅ She read the results twice before she answered.
✅ The architecture is three services and one queue.
✅ Keep one of the paired abstractions, or neither.
```

**Default action** — name the concrete thing and cut the wrapper noun. The `the [adj] [noun] of [possessive]` shape does not survive surgery: rewrite the sentence from scratch. For paired abstractions, keep one.

**Keep when** — the wrapper is a counting or set expression rather than an abstraction (`a set of flags`, `a list of paths`, `a pair of sockets`, `a copy of the manifest`); the abstraction is the actual subject matter (legal, policy, philosophy); quoted material; a fixed term of art.

**Boundary with rule 21** — rule 21 hunts empty verb + nominalization (`perform an analysis of`); this rule hunts noun wrapping noun. One sentence can hit both. Fix each once; do not count the same span into two densities.

**Reread** — check you have not replaced every wrapper with the same concrete verb. Uniform repair is rule 18's skeleton signal wearing new clothes.

## 29. Unclear pronouns `[EN]`

**Pattern** — `this` / `it` / `they` whose antecedent is a whole preceding clause, or sits two or more sentences back; a pronoun that could bind to either of two nouns already in the sentence. Professional editors fix these under awkward word choice (28%, LAMP-2025).

```
❌ The job retries the upload and then rewrites the manifest. This is what broke the deploy.
❌ The parser hands the buffer to the writer before it flushes.
```

```
✅ The job rewrites the manifest after the retry. The rewrite is what broke the deploy.
✅ The parser hands the buffer to the writer before the writer flushes.
```

**Default action** — replace the pronoun with the noun, and use **the noun the text already used**. Do not upgrade to a synonym or a category word (`the parser` → not `the component`); that trades this rule for rule 22.

**Keep when** — the chain is unambiguous and short; dummy `it` (`it turns out`, `it rains`); idiomatic `this` inside dialogue; quoted material.

**Reread** — repeating the noun three times in three sentences is normal human writing, not a new problem. Only reach for a pronoun again when the reference cannot be misread.

## 30. Run-on and tangled sentences `[EN]`

**Pattern** — three or more finite clauses strung together with commas, `and`, or `which`; a comma splice; a `which` clause that modifies the whole preceding clause instead of a noun. 20% of professional edits (LAMP-2025).

```
❌ We rolled the change back and the queue drained within minutes, which meant the on-call could stop paging people, and by then the root cause was obvious.
```

```
✅ We rolled the change back and the queue drained within minutes. The on-call stopped paging people. By then the root cause was obvious.
```

**Default action** — split. One tangled thought becomes two plain ones. Split where the **subject changes**, not at the longest comma.

**Keep when** — the sprawl is voice work the venue actually uses (verified from the venue corpus, not assumed); legal or spec text where the clause chain is the definition; quoted material.

**Do not port to Chinese.** Chinese runs clauses on by design; clause counting there produces false positives. Chinese long sentences are governed by rule 18 (rhythm), not by this rule. (`inference` — neither parent measures Chinese clause length.)

**Reread** — rule 18. Three split sentences in a row of near-equal length is a new finding, not a finished fix.

## 31. "Seem to + verb" and needless hedge verbs `[EN]`

**Pattern** — `seems to` / `appears to` / `tends to` / `serves to` / `works to` / `helps to` + verb, where the source asserts the thing outright.

```
❌ The patch seems to reduce p99 latency.
❌ This approach tends to work well for large repositories.
```

```
✅ The patch reduces p99 latency.
✅ This approach works for large repositories over ~50k files.
```

**Default action** — use the verb itself.

**Hard limit** — a hedge is truth-bearing. Removing one the source meant hardens a claim, which is a fact change and is forbidden at every force level and every scope. When you cannot tell whether the uncertainty is real, **keep the hedge and flag it**; never resolve the ambiguity by asserting.

**Keep when** — the uncertainty is genuine; the venue requires it (postmortems before root cause is confirmed, academic writing, safety notices); quoted material. Hedge once per genuinely fragile claim, not once per sentence — a hedge on every sentence is its own tell.

## 32. Filter words `[EN]`

**Pattern** — a perception verb standing between the reader and the event: `felt`, `seemed`, `realized`, `noticed`, `knew`, `saw`, `heard`, `watched as`.

```
❌ She felt the cold seep under the door.
❌ He noticed that the queue was still growing.
```

```
✅ The cold seeped under the door.
✅ The queue was still growing.
```

**Default action** — delete the filter and render the thing directly.

**Keep when** — **the perception itself is the fact.** In `docs` / `status` / postmortems, "the on-call noticed the alert at 02:14" reports an event with an actor and a timestamp; deleting `noticed` deletes the responsible party, which the truth-preserving contract forbids. Also keep for unreliable narration, and wherever the gap between what happened and what the POV character registered is the point. Quoted material keeps its texture.

**Scope** — fiction-first. In professional prose, treat a hit as a finding only when the sentence has no observer worth naming.

**Authority split** — the word list lives in `style-pass.md` §3; this rule owns the operation and the professional carve-out.

**Confidence** — the list is a community corpus (FICTION-RP-COMMUNITY), not a measurement; the professional carve-out is `inference`.

## 33. 版面與標記痕跡 `[structural；Title Case 子項為 EN-only]`

**模式**：用 markup 本身製造「這篇很用心」的表象。第 13、14、26 條管的是中文文體的量化上限，本條管的是**標記層的形狀**，判準是場地慣例而不是通用禁令。

**訊號**：

- 用「**粗體迷你小標**：一句說明」的條列，去寫本來一段散文就說得完的事
- emoji 當裝飾（標題前、列點前、句尾）
- `Title Case` 標題（**EN-only**；中文母體段自動退出這個子項）
- 每一節長度都差不多
- 到處都是剛好三項的清單（句內的三件套是第 7 條；這裡管的是整份文件反覆出現同一個三）
- 小標題被它的第一句原樣覆述（`## 快取策略` → 「這一節說明快取策略。」）
- 分形摘要：每一層都先預告、再說、再收一次

**預設動作**：**對齊場地實際的排版習慣，不是套通用禁令。** 取樣 2–3 篇同場地、確定人寫的近期文字，照它們的慣例辦——README 本來就有小標與清單就留；某個 repo 的 release note 本來就用 emoji header 就留。場地慣例只管版面，**不管用詞與標點**：第 1 層優先於場地模仿。

沒有場地語料時才退回基線：粗體迷你小標併回段落、裝飾性 emoji 刪除、覆述型首句刪除、分形摘要只留最靠近內容的那一層、`Title Case` 標題改成該場地的大小寫慣例（多數技術場地是 sentence case）。

**保留條件**：使用者自己先用 emoji 或明確要求；場地語料證實的慣例；技術文件裡粗體標示參數名或警告等級的固定格式；`scene-packs` 裡本來就靠版面導覽的體裁。

**與第 13、14、26 條的關係**：那三條給數字上限，本條給場地判準。衝突時以場地語料為準。英文段落不套第 26 條的字數門檻，一律走本條。

**信心**：Formatting 這一類線索的提及率 15.0% 是 `grounded`（RUSSELL-DETECT-2025，英文非虛構 300 篇）；細目清單來自 WIKIPEDIA-AI-WRITING，是編輯經驗不是量測（`inference`）；「對齊場地慣例」這個處方是 `inference`。

## 34. 版面位置痕跡 `[structural]`

**模式**：東西擺在版面上的位置，比用詞更能出賣機器。

| 位置 | 機器習慣 | 人的習慣 |
|---|---|---|
| 段落長度 | 均一 | 參差，包含至少一個單句段落 |
| 引語與關鍵句 | 永遠收在段尾 | 任何位置，包含段中 |
| 性質、理由、意象的列舉 | 剛好三項 | 兩項、四項、一項；三項只是其中之一 |
| 場景／小節轉場 | 每次同一個連接公式 | 換著來：硬切、時間跳、對話接住 |
| 強調 | 平均分佈 | 集中在真正重要的地方，其餘不強調 |

**為什麼要單獨立一條**：位置痕跡比用詞耐改寫。在 RUSSELL-DETECT-2025 裡，整篇改寫（paraphrase）之後，位置線索對專家讀者變得**更**明顯，不是更少。只換詞不動位置，等於把最耐用的那層痕跡原封留著。

**預設動作按 edit scope 降級**：

| scope | 能做到哪 |
|---|---|
| `structural` | 自由合併、拆分、重新分段。直接做出參差，至少留一個單句段落；把每次一樣的轉場換成不同方式；把強調收攏到真正該重的地方 |
| `bounded` | 只做句內拆分與刪子句。段落切分、重新分段、關鍵句位置調整**一律只回報不執行**，寫在刪除清單旁的觀察欄，由使用者拍板 |
| `in-place` | 全部只回報，不動任何段落邊界 |

純標記層的動作（裝飾性 emoji、多餘的粗體標記）不算段落結構：`bounded` 可直接執行；`in-place` 只有在不刪任何字面文字、不動句子邊界時才執行，否則一併回報。

**保留條件**：場地慣例本來就是均一段落（API 參考、規格表、變更記錄的逐條列）；表格與清單本來就該對齊；引語位置由引用規範決定；使用者自己提供的原始分段。

**回讀**：改完重數一次段落長度序列。原本 4-4-4-4 改成 6-2-5-3 算完成；改成 4-4-4-1 只是尾巴掛了一個短段，痕跡還在。

**信心**：「位置痕跡耐改寫」`grounded`（RUSSELL-DETECT-2025，英文非虛構，專家讀者）；中文段落沿用是 `inference`；scope 降級階梯是本 skill 的機制，與量測無關。
