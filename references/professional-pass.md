# Professional pass — shared non-fiction layer

Applies to every non-fiction document in either language: release notes, README, PR/issue replies, code-review comments, postmortems, tickets, API reference, FAQ, forum posts, technical articles, and anything else that is not narrative. Evidence: the slop taxonomy (Shaib et al., S), expert AI-detector studies (Russell et al., R), genre-alignment findings (Reinhart et al., P), and the Wikipedia/humanizer corpus of documented tells (W). Stable source identities live in the repository research ledger; single-letter aliases here are file-local.

**Confidence tags used below:** `[grounded]` = follows from a measured claim in a source; `[inference]` = reasonable extension, usually cross-language; `[speculative]` = design judgment with no measurement behind it. Every source cited here measured **English** text. The checklist's applicability to ZH-matrix spans is `[inference]` throughout — there is no Chinese measurement baseline in either parent skill, and this file does not manufacture one.

> The goal is not to fool a detector. It is that the text carries information, has a stance, and sounds like it came from the person whose name is on it. Conventional structure is fine here; slop is the filler inside the structure.

## Read the venue first

Before writing or editing, sample 2–3 recent artifacts from the same venue that a human demonstrably wrote — this repo's past release notes, this maintainer's recent replies, this team's last postmortem. Instruction-tuned models favour a dense, noun-heavy register and do not match genre-aligned variation (P) `[grounded]`, so the venue corpus, not this skill, defines the target voice. With no corpus, the scene pack's baseline applies.

**Sample for these, and only these:**

| Sample | Do not sample |
|---|---|
| Structure (what sections exist, in what order) | **Vocabulary** |
| Length norms (how long a normal entry runs) | **Punctuation** |
| Formatting habits (tables vs prose, code fences, footers) | |
| Heading and severity conventions (`### Fixed`, `P1`, `SEV-2`, `[BREAKING]`) | |
| How credit and links are given (`thanks @x`, `(#412)`, trailer lines) | |

**Layer 1 outranks corpus mimicry** `[inference]`. If the sampled Chinese artifacts use mainland vocabulary (視頻／軟件／信息／數據 as data／質量 as quality／用戶／默認／項目／優化／調用／網絡／智能) or half-width punctuation inside Chinese prose, inherit neither. A venue's habits are not evidence about usage correctness; matching them there would put an error into the output on purpose.

**The one legitimate ask.** When the target venue is demonstrably a mainland-usage project and the user is publishing into it, ask **once** which usage standard governs, then record the answer in the report header. Constraints on that ask `[inference]`:

- Ask once per document, not per occurrence. The answer covers the whole document.
- The answer binds **vocabulary and punctuation together**. Never apply one standard to vocabulary and the other to punctuation — a document with 用戶 and 「」 alongside half-width commas reads as broken in both standards.
- Never switch standard silently, in either direction. Taiwan → mainland and mainland → Taiwan both require the user's answer.
- No answer available (headless run, user unreachable) → keep the Layer 1 default, finish the work, and state in the report that the question is outstanding.

## The checklist

Runs on **both languages**. Run the checks **one at a time — a combined pass goes blind**, measured on this very taxonomy (S) `[grounded]`.

Density is **cumulative**: one hit is not a verdict, and the count is what decides. The thresholds are numeric and live in [`severity.md`](./severity.md) — Tier 1 default-replace, Tier 2 same-paragraph clustering, Tier 3 whole-document density, counting characters for Chinese and words for English, with code, paths, and version numbers each counting as one unit. Use those numbers here; do not re-invent a per-domain feel for "too many".

| # | Check | What to hunt |
|---|---|---|
| 1 | Chatbot residue | EN: "Great question", "Thanks for raising this!", "I hope this helps", "Certainly!", "You're absolutely right", apology openers, offers of further help, "Let's dive in". ZH `[inference]`: 「好問題」「感謝提出」「希望這對你有幫助」「當然可以！」「你說得完全正確」「讓我們一起來看看」. Delete — a colleague does not talk like a support desk. **Tool signatures count as residue**: `🤖 Generated with …` footers and AI `Co-Authored-By:` trailers — see the note below. |
| 2 | Density | Could this say the same at half the length? Statements true in any context carry zero information — EN "in today's fast-paced world", "it's important to note"; ZH 「在當今快速變化的環境下」「值得注意的是」. Length must be proportional to stakes. |
| 3 | Relevance | Does every paragraph serve *the reader's task* — the thing they opened this to find out? Background the reader already has, restated questions, and scope tours are filler. |
| 4 | Stance | Where a judgment is required, commit to one. Absent subjectivity is a measured slop dimension (S) `[grounded]`: a review with no verdict, a comparison with no recommendation, a postmortem with no admitted mistake. Hedge once per genuinely fragile claim, not once per sentence. |
| 5 | Specificity | Versions, numbers, `file:line`, commands, verbatim error text, names — present and **real**. Never pad with invented specifics; a wrong fact stated confidently is itself a top-tier tell (R) `[grounded]`. Missing information → ask, or leave an explicit TODO. |
| 6 | Formatting tells | Bold-mini-heading bullet lists where prose would do; emoji as decoration; **Title Case headings (English-only item)**; every section the same length; lists of exactly three, everywhere; a heading restated by its first sentence; fractal summaries — announce → say → recap at every level (W). |
| 7 | Conclusion residue | EN: "In conclusion/summary" sections, restating what was said, generic outlook ("we will continue to improve…"). ZH `[inference]`: 「總的來說」「綜上所述」「歸根結底」「未來我們會持續優化」（此處連支語一起處理）. End when the content ends. |
| 8 | Templatedness | The same sentence frame recycled ("X, a Y at Z, said that…" three times over); every list item phrased identically. Vary it, or turn it into a table. |
| 9 | Sameness of rhythm | Uniform paragraph and sentence lengths throughout. Human professional prose is uneven — depth where it matters, one-liners where it does not. |
| 10 | Fluency | Grammatical but unsayable ("the earthen area that formerly held the puddle"). Read it aloud. If nobody would say or write it in a message to a colleague, redo it in speech-shaped syntax. |
| 11 | Portability ／ 可攜性 `[inference]` | Paths, commands and config that are **specific but true only on the author's machine**: absolute paths rooted in a personal layout (`D:\Claude\mytool\`, `/Users/alice/dev/`), drive letters, hostnames, ports, network shares. Hides behind check 5 — see the note below. |

**Check 6, Chinese spans, one carve-out** `[inference]`: half-width punctuation and mainland vocabulary inside Chinese prose are **Layer 1 correctness**, not check-6 findings. Fix them, do not report them as style findings, and do not let them consume a calibration move or a report slot.

### Check 11 in full — 「具體」不等於「可攜」 `[inference]`

Check 5 rewards concreteness, and that is precisely why check 11 gets missed: an absolute path **looks like** the specificity check 5 asks for. It reads as authoritative, it survives review, and it is wrong for every reader who is not the author. Specificity that holds on exactly one machine is not specificity — it is local state that leaked into the document.

**The decisive test is one question**: could a reader who just cloned the repo, or who just installed the product, run this line as written? If not, it is a defect no matter how concrete it looks.

| 保留絕對路徑 | 改掉 |
|---|---|
| 由軟體或平台決定、每個讀者都一樣的位置 —— 安裝根目錄、`C:\ProgramData\…`、`/etc/`、`%APPDATA%\…`、服務自己的資料目錄 | 作者的 clone 位置或工作目錄 |
| 工具自己在固定位置建立的檔案 | 個人的磁碟機代號與家目錄 |
| 讀者真的需要的站點基礎設施（公司網路磁碟機）—— 但**標明它是站點限定**，讓不在那個站點的人知道跳過，而不是去找一個不存在的分享 | 只是某一次部署選擇的主機名、連接埠、分享名 |

Replacements, in order of preference: the repo-relative form (`python tool.py`), a stated placeholder (`<repo>`、`<專案>`、`$CDSROOT`), or an environment variable the document already defines. When you make commands relative, **say where they are run from** — one line, once, in the section that carries them.

**Staleness is a second and sharper signal.** When the documented path disagrees with where the project actually lives now, the path has been wrong long enough that nobody has run the document's own instructions. Report that as a finding, not just as an edit — it tells the author something about the document that the fix alone does not.

**回讀檢查**：搜尋磁碟機代號、`~`、`/home/`、`/Users/`、主機名。每一處問同一個問題 —— 這個位置是平台定的，還是作者定的？只有前者留下。

This is a **per-instance correctness finding, not a density judgment**: one bad path is one defect. Do not give it a Tier number and do not wait for a cluster. Evidence class is editorial heuristic from observed cases; nothing measured stands behind it.

### Tool signatures and authorship trailers `[inference]`

A generator's own signature left in the artifact is the purest form of check-1 residue, and it is the one form that carries a consequence beyond style:

- `🤖 Generated with …` footers in a PR body or a commit message.
- `Co-Authored-By:` trailers naming an AI tool.
- 「本文由 AI 協助撰寫」 style disclaimers appended by habit rather than by a venue that requires them.

**Default: remove them.** `Co-Authored-By:` lists **real people only** — the configured git author, the signed-in account, or a collaborator the user actually named. With no second human to credit, the line does not exist.

Why this is a fidelity matter and not a taste one: commit history and PR metadata are an **attribution record**. A tool trailer writes into the responsibility chain an entity that made no judgment and carries no consequence, and it distorts `git blame`, contribution statistics, and who is accountable at review. So it is handled like Layer 1 correctness — **it does not consume a calibration move, and no edit scope exempts it**, `in-place` included.

Two limits on this rule:

- **The user's own instruction wins.** If they ask for a specific trailer or disclaimer, add it. This rule governs what you attach *by default*.
- **A venue that genuinely requires disclosure gets the disclosure.** Some journals, contests, and employers mandate an AI-use statement. That is a venue requirement, not residue — keep it, and keep it where the venue puts it.

Full venue rules in [`packs/_scene-packs-zh.md`](./packs/_scene-packs-zh.md) `commit-message`.

Then finish with the vocabulary and syntax scan, routed by matrix language: EN-matrix spans → [`style-pass.md`](./style-pass.md) §2–3 (the ban tables apply to professional prose; the fiction-slop row does not); ZH-matrix spans → [`phrases-zh.md`](./phrases-zh.md) and [`structures.md`](./structures.md).

## Domain weighting

Which checks dominate depends on document shape (measured: S) `[grounded]`; the weighting carries over to Chinese unchanged `[inference]`.

| Document shape | Weight first |
|---|---|
| Article-like (postmortem, tech article, announcement, README) | Relevance, density, stance/tone, coherence |
| Short answers (PR/issue replies, review comments, tickets) | Factuality, specificity, templatedness — density and tone matter less at short length |

Weighting sets order and depth of attention, not exemption: a short reply drowning in filler still fails density.

For long-form (articles, postmortems), also run the outline test and QUD check in [`discourse-pass.md`](./discourse-pass.md) §1–3 — extract the first sentence of each paragraph; a clean-summary outline, and a briefing → justification → consequences → reflection question-sequence, are both machine shapes.

## Unsourced claims — pack rules win

The general unsourced-quotation modes (`rewrite-safe` / `audit-only` / `rewrite-with-placeholder`) are the floor. **Where a professional scene pack is stricter, the pack governs** `[grounded]` — each of these is a stated pack rule, not an extrapolation:

| Pack | Rule that overrides `rewrite-safe` |
|---|---|
| release-note | Every claim carries its artifact — issue/PR number, commit range, exact version string. **No artifact → no claim.** The claim goes, not just its number. |
| tech-article | Benchmarks carry their conditions — machine, version, dataset size, number of runs. **No conditions → do not print the number.** |
| postmortem | Duration, blast radius, user and request counts come from the real incident data, **never estimated to sound complete**. |

Why this matters: `rewrite-safe` would let you strip the unsupported attribution and keep whatever judgment still stands on its own. In these three packs that is not enough — the surviving sentence would still be a published claim with nothing behind it. Delete the claim, or go get the artifact. And the override never runs the other way: it does not license inventing a condition, a run count, or an incident number to satisfy the rule. Missing → ask the user, or ship an explicit TODO.

## Report format (`review` operation)

```text
BE-HUMAN REVIEW — <document type> @ <venue>
Venue corpus: <2-3 artifacts sampled | none — using scene-pack baseline>
Usage standard: <只在問過時才印這行：Taiwan (Layer 1 default) | mainland — 使用者於本次確認>

[1] 問題族：<開場套話／密度／無源引用／格式指紋／語域混搭／材料不足／…>
    觸發點：「<逐字引用原文>」        ← 引不出原文就不是發現
    建議動作：<刪掉／換成具體資訊／補來源／保持不動>
    是否建議改寫：<是／否>

[2] …                                  ← 最多 5 條，最嚴重的排前面

Verdict: <clean | isolated hits | cluster> → <ship | refactor | recreate>
```

Rules for the block:

- **1–5 findings, hard cap.** More than five means the verdict is `cluster` and the answer is `recreate`, not a longer list.
- **`觸發點` must quote.** No verbatim quote, no finding. This holds for English documents too — the field name is Chinese, the quoted evidence is in whatever language the span is.
- The verdict maps to the next operation and nothing else: `clean → ship`, `isolated hits → refactor`, `cluster → recreate`.
- No "Passed:" line. Listing the checks that found nothing is noise, and it invites padding the failed list to look balanced.
- Findings only. Do not attach a full rewrite to a `review`.

## Whitelist — conventional ≠ slop

| Do not flag | Why |
|---|---|
| Changelog categories, issue/PR templates, RFC sections, runbook formats | Formulaic containers by convention; the community expects them |
| Formal register in a formal venue | Register match beats forced casualness |
| Bullets for genuinely enumerable items | Tables and lists are correct for enumerable facts |
| Terse, unadorned replies | Brevity is the human default in dev venues, not a tell |
| The author's own verified habits | Edit toward their voice, not a generic "human" |

The full false-positive set — quoted source text, term-under-discussion, code and identifiers, industry-standard senses, non-human subjects in system descriptions, engineering vocabulary in incident reports, English words embedded in Chinese sentences — is in [`severity.md`](./severity.md) 誤殺防護 and [`boundary-cases.md`](./boundary-cases.md).

## 中文場景說明

中文母體的專業文字除本檔外，另看 [`packs/_scene-packs-zh.md`](./packs/_scene-packs-zh.md) 與 `packs/zh-*.md`：事故檢討看 [`zh-postmortem.md`](./packs/zh-postmortem.md)、工單看 [`zh-ticket.md`](./packs/zh-ticket.md)、技術文章看 [`zh-tech-article.md`](./packs/zh-tech-article.md)、程式碼審查意見看 [`zh-code-review.md`](./packs/zh-code-review.md)。這些包拿英文包的結構骨架（時間線、失效機制、行動項、驗收條件），用詞走臺灣用語，不是把英文包翻譯過來——直接翻譯會從事故詞彙把支語帶進來（復盤→事後檢討、根因→根本原因、對齊→同步、落地→實作、顆粒度→細緻程度）。`RCA`、`SLA`、`P0`、`blocking` 這類識別碼保留英文。

本檔的十項檢查對中文母體段一樣要跑，但上面每一條的中文示例都是設計推論：兩個上游都沒有中文語料的測量基線，所以不得在報告裡把中文的判斷寫成實測結果，也不得對中文文字做模型歸因。
