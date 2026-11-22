# AGENTS.md：MR 論文 LLM Wiki 規範

版本 v0.2（2026-11-22）。本檔是這個 wiki 的 schema，寫明目的、結構、流程、煞車與審查。
Claude Code 透過 `CLAUDE.md` 裡的 `@AGENTS.md` 讀到本檔；Codex 等工具直接讀本檔。
做法參考 Karpathy 的 LLM Wiki：你負責找來源、提問、判斷；agent 負責摘要、交叉連結、歸檔與維護。

## 0. 先講清楚的名詞

| 詞 | 意思 | 例子 |
|---|---|---|
| 目標 | wiki 要幫你做到的事 | 從 wiki 直接整理出 related work |
| 限制 | 任何時候都不能違反的規則 | raw/ 唯讀、不捏造引用 |
| 完成標準 | 做到就停，不再加工 | ingest 的自我檢查全部通過 |
| 煞車 | 還沒做完，但必須停下來問你 | 一篇要改超過 15 頁；證據只有公司自稱 |
| 停止條件 | 整個主題或專案該停或該轉向 | 某主題連續 3 篇沒有新東西 |
| 觸發 | 什麼事件啟動什麼動作 | 你說「ingest」就執行 Ingest |
| 審查 | 誰、什麼時候、檢查什麼 | 每批 ingest 後產生審查清單 |

兩個前提：
- agent 看不到自己用了多少 token 或錢。本檔的成本煞車都用看得到的指標：讀了幾頁 PDF、改了幾個 wiki 頁、對外查了幾次。真正的金額上限請在帳號端設定。
- 每個 session 都會讀一次本檔，所以本檔要保持精簡；範本放在 `templates/`，要用時才讀。

## 1. 目標與非目標

目標
- G1 Related work 地圖：6 個 pipeline 步驟與 3 個研究問題，各自整理「已有方法、做得到什麼、做不到什麼」，每一句都追得到來源。
- G2 缺口：寫清楚每個研究問題還沒解決的部分，並分開「來源說的」與「推論的」。
- G3 平台與市場現況：頭戴裝置相機權限、即時生成模型、XR 硬體與創作者市場；每條附日期，過期會被標出。
- G4 累積：值得留的問答、比較、分析存回 wiki，不必重做。

非目標
- 不寫 MR 系統的程式碼。
- 不寫論文正文。寫作交給 paper 系列 skills，wiki 只提供有出處的材料。
- 不收你自己的專案紀錄、實驗數據、會議筆記（2026-11-22 決定，見 §13）。
- 市場資料只當研究背景，不提供財務或職涯建議。

## 2. 研究框架（每次 ingest 都用這個角度讀）

出處：你的系統願景草稿（2026-10-27，原檔 `system_vision.md`，不在此 vault）。它是框架，不是證據，wiki 裡不能引用它來支持事實。

願景：MR 系統辨識真實物體與牆面，依使用者描述的個人風格，用生成式 AI 產生新外觀，貼回真實物體並跟著移動。核心是「真實物品被你的風格改造」；浮動視窗類功能現有頭戴裝置已有，不是獨特之處。

Pipeline 六步驟（hub 頁在 `wiki/pipeline/`；「目前狀態」是背景資訊，不是證據）

| ID | 步驟 | 內容 | 目前狀態 |
|---|---|---|---|
| step-1-segment | 找出物體 | 影像分割 | 有（Repaint，MediaPipe） |
| step-2-locate | 知道它在哪 | 追蹤、深度、平面偵測 | 部分（Scaffold XR 平面偵測；朝向的鏡像問題待驗證） |
| step-3-generate | 生成新外觀 | 擴散模型依風格描述生成 | 未做 |
| step-4-composite | 貼回去 | 透視變換、遮罩、混色、光線 | 簡化版（Multiply） |
| step-5-stability | 穩定與低延遲 | 逐幀一致、不閃爍 | 最難；Repaint 延遲 130–135 ms，連續模式不穩 |
| step-6-control | 使用者下指令 | 文字、選項 | 部分 |

研究問題（hub 頁在 `wiki/rq/`）
- rq1-waiting：生成速度慢時，等待期間空間該呈現什麼（延續 Scaffold XR）。
- rq2-stability：如何讓改造在移動與光線變化下保持穩定。
- rq3-style-control：如何讓使用者精確控制「風格」，而不是每次碰運氣。

範圍
- 近期做：一件平面物品的風格改造加牆面；手機瀏覽器 demo；量測延遲與閃爍。MVP-1 物件是筆電蓋，備案是海報。
- 暫不做（標 `deferred`）：多視窗與應用程式、整個空間即時生成、頭戴實機。
- 未來可能：行事曆、待辦、筆記等日常應用。

平台與市場主題（放在 `wiki/entities/`，subtype 為 platform、company 或 device）：頭戴裝置相機存取（Quest、Android XR、Vision Pro、Snap Specs）、即時生成影片、XR 硬體出貨、AR 創作者收入。

## 3. 限制（任何時候都不能違反）

- C1 raw/ 唯讀：不修改、不移動、不改名、不刪除。
- C2 不捏造：引用、作者、年份、venue、數字、頁碼只能來自 raw/ 的原檔，不從模型記憶補。
- C3 寫入範圍：只寫 `wiki/`。改 `templates/` 或本檔要你先同意。
- C4 不刪 wiki 頁：要合併或廢棄就加 `status: deprecated`，並連到新頁。
- C5 不自動 ingest：你說了才做。
- C6 事實與推論分開：推論一律放在 `> [!inference]` 區塊。
- C7 你手動改過的內容優先：不覆蓋；有衝突就寫進審查清單。
- C8 不把 vault 內容送到外部服務；搜尋關鍵字不放個人資料。
- C9 git 只做 commit 與 revert：不 reset、不改寫歷史、不 push。revert 要你先同意。

## 4. 資料夾結構

```
LLM wiki/
├─ AGENTS.md         本檔
├─ CLAUDE.md         只有 @AGENTS.md，讓 Claude Code 讀到本檔
├─ .gitignore        不進 git 的檔案：Obsidian 視窗狀態、PDF、raw/assets/
├─ templates/        頁面範本：source、concept、entity
├─ raw/              原始資料，唯讀；你負責放檔案
│  ├─ papers/        論文、預印本、技術報告（PDF）
│  ├─ articles/      技術文章、部落格（Web Clipper 存成 .md）
│  ├─ news/          平台與市場新聞
│  └─ assets/        圖片附件
└─ wiki/             agent 負責寫，你負責讀
   ├─ index.md       目錄，每頁一行
   ├─ log.md         時間序紀錄，只能往後加
   ├─ overview.md    研究全貌與目前論點
   ├─ pipeline/      6 個步驟的 hub 頁
   ├─ rq/            3 個研究問題的 hub 頁
   ├─ sources/       每個來源一頁
   ├─ concepts/      沒有專有名稱的概念、問題、技術，例：temporal-consistency
   ├─ entities/      有名字的東西：模型、系統、資料集、裝置、平台、公司
   ├─ questions/     存回來的問答、比較表、分析
   └─ review/        批次審查清單、lint 報告
```

- wiki 檔名一律英文小寫加連字號。來源頁用 `YYYY-作者或機構-關鍵字.md`，例：`2025-decart-miragelsd.md`。
- raw/ 檔名由你決定，agent 不改；建議同樣用 `YYYY-作者-關鍵字`。

## 5. 頁面規則

### 5.1 語言
- 英文在前，頁尾放 `## 中文說明`。
- 中文說明是 3–6 點重點，不是逐句翻譯，以控制長度與 token。
- 論文標題、引文、專有名詞保留原文。
- index.md 每行格式：`[[頁名]] — English summary｜中文短語`。

### 5.2 證據等級（每個事實句都要對到其中一級）

| 標籤 | 意思 | 寫法 |
|---|---|---|
| `peer-reviewed` | 期刊或會議論文 | 可寫成事實 |
| `preprint` | arXiv、技術報告 | 可用，但註明是預印本 |
| `vendor-claim` | 公司官方文件、部落格、發表會 | 只能寫「X 宣稱……」 |
| `news` | 媒體報導 | 寫明媒體與日期；轉述的數字標原出處 |
| `rumor` | 傳聞、未證實 | 只能放在 entity 頁的「Rumors」段，不得進 overview |
| `inference` | agent 或你的推論 | 放在 `> [!inference]` 區塊 |

### 5.3 引用
- 句尾寫 `([[2025-decart-miragelsd]], p.3)`；新聞沒有頁碼就寫段落標題。
- 數字要附條件：硬體、解析度、資料集、日期。缺條件寫 `conditions unknown`。
- 作者、年份、venue、DOI 只從原檔讀；不確定就寫 `TODO`。

### 5.4 Frontmatter
- 所有頁：`type`、`updated`。
- source 頁與 question 頁另有 `review: pending | approved`；source 頁的完整欄位見 `templates/source.md`。
- 新聞、平台、公司、裝置相關的頁必填 `as_of`。
- `flags` 可用值：`single-source`、`out-of-scope`、`deferred`、`stale`、`conditions-unknown`、`partial-read`、`saturated`。

### 5.5 什麼時候開新頁
- 概念或實體被 2 個以上來源提到，或是某個步驟或研究問題的核心，才開新頁；否則只在來源頁裡提。
- 同一個概念只有一頁，別名放 `aliases`。
- 不刪頁，見 C4。

## 6. 操作流程

### 6.1 Session 開始（只在要做 wiki 操作時）
1. 讀 `wiki/index.md` 與 log 最後 5 筆：`grep "^## \[" wiki/log.md | tail -5`。
2. 列出 raw/ 裡還沒有對應來源頁的檔案（比對來源頁的 `raw:` 欄位）。只列，不 ingest。
3. 數 `review: pending` 的來源頁數；有就提醒你。
4. 上次 lint 之後已 ingest 10 篇以上，就建議 lint。
5. 不讀頁面內文。

### 6.2 Ingest（單篇）
1. 讀來源。PDF 超過 20 頁時照 B3 處理。
2. 照 `templates/source.md` 寫來源頁：摘要、主要主張（附頁碼與證據等級）、數字與條件、與本論文的關係（哪個步驟、哪個研究問題）、作者自述的限制、中文說明。
3. 更新相關的 pipeline、rq hub 頁與 concept、entity 頁；不需要改就在來源頁寫 `no hub update`。
4. 新來源和舊說法衝突時，舊說法保留，兩者並列並標 `> [!contradiction]`，列入審查。
5. 更新 index.md，在 log.md 加一筆。
6. 跑 §9.1 自我檢查，回報改了哪些檔。

### 6.3 Ingest（批次）
- 一批最多 5 篇，依序處理，不開 subagent。
- 每篇照 6.2 做，但中途不停下來討論；需要你決定的事寫進審查清單。
- 整批結束後產生 `wiki/review/YYYY-MM-DD-batch-N.md`（格式見 §9.2）。整批來源頁都是 `review: pending`。
- 單篇遇到資料問題（讀不出來、只有摘要）：標記、跳過，繼續下一篇。
- 遇到成本煞車：做完手上這篇，停下整批。

### 6.4 Query
1. 先讀 index.md，再開相關頁，最多 10 頁（B7）。
2. 回答要引用 wiki 頁與來源，並標證據等級；說清楚哪些部分 wiki 沒有資料。
3. wiki 不夠回答時照 D5 處理，不用模型記憶補。
4. 答案值得留（比較、分析、新連結）就問你要不要存成 `wiki/questions/` 的頁；存的頁是 `review: pending`。

### 6.5 Lint
產生 `wiki/review/YYYY-MM-DD-lint.md`，檢查：
- 頁面之間的矛盾；被新來源取代的說法。
- 孤兒頁（沒有其他頁連進來）、壞連結、index 漏列。
- 被提到 2 次以上但還沒有頁的概念。
- 覆蓋表：6 個步驟、3 個研究問題各有幾個來源，以及證據等級分布。
- `as_of` 超過 6 個月的頁。
- overview 與 rq 頁中只有單一來源支持的句子，或引用了 pending 來源的句子。
- `review: pending` 超過 14 天的頁。
- 飽和：某步驟最近 3 個來源都沒有新主張。

機械性修正（壞連結、index 漏列、frontmatter 格式）直接改；內容修改只列建議，等你同意。需要上網補的地方只列「建議搜尋」，不自己搜。

### 6.6 Git（每個寫入操作一個 commit，方便整批還原）
- 開始寫入前跑 `git status`。有未 commit 的變更（通常是你手動改的），先 commit 成 `manual: edits before <操作>`，不要混進 agent 的 commit。
- 每個操作結束後 commit 一次，訊息格式：
  - `batch-N: ingest K sources`（審查清單裡記下這個 commit hash）
  - `ingest: <來源頁名>`
  - `lint: mechanical fixes`
  - `review: approve batch-N`
  - `schema: <改了什麼>`
- 你退回整批時：agent 提出 `git revert <hash>`，你同意才執行，然後在 log 記 `## [日期] review | batch-N reverted`。revert 會留下紀錄，日後還可以再還原。
- PDF 與 `raw/assets/` 不進 git（見 `.gitignore`）；原檔請你自己另外備份。

## 7. 觸發

| 事件 | 動作 |
|---|---|
| 你說「ingest 某檔」 | 單篇 Ingest（§6.2） |
| 你說「ingest batch」或給多個檔名 | 批次 Ingest（§6.3），最多 5 篇 |
| 開始一個要做 wiki 操作的 session | Session 開始檢查（§6.1） |
| 你問問題 | Query（§6.4） |
| 答案值得留 | 問你要不要存到 questions/ |
| 上次 lint 後 ingest 滿 10 篇、要寫論文某一章前、或你說「lint」 | 建議或執行 Lint（§6.5） |
| 批次結束 | 產生審查清單（§9.2） |
| 遇到成本、資料或範圍問題 | 對應的煞車（§8） |
| 你回覆「approve batch-N」或指定頁名 | 把那些頁改成 `review: approved`，log 記一筆 |
| agent 發現規則不好用 | 提出本檔修改（§12） |
| 專案檢查點日期已過 | 提醒你一次（§11） |

## 8. 煞車

煞車時一律照 §8.4 做。不能用「拆成小份分次做」來繞過煞車。

### 8.1 成本煞車（保守，2026-11-22 決定）

| ID | 條件 | 動作 |
|---|---|---|
| B1 | 單篇 ingest 要新增或修改超過 15 頁 | 停，列出想改的頁，問你要改哪些 |
| B2 | 一批超過 5 篇，或整批累計改動超過 30 頁 | 做完手上這篇就停，回報剩下的 |
| B3 | PDF 超過 20 頁 | 只讀摘要、引言、結論與圖表標題，標 `read_depth: partial`；問你要不要讀全文（批次時寫進審查清單） |
| B4 | 一個 session 對外查詢（網路搜尋或抓網頁）超過 3 次，或要用 extended 搜尋 | 先問 |
| B5 | 想開 subagent | 只有你在對話中明確要求才開 |
| B6 | Lint 要讀內文的頁超過 20 頁 | 先問；預設只讀 frontmatter 與被標記的頁 |
| B7 | Query 要開超過 10 頁 | 先用已讀的頁回答，說明還有哪些沒看，問要不要擴大 |
| B8 | 要重讀已 ingest 的原檔全文 | 只讀要查證的那一段；整篇重讀要先問 |
| B9 | 同一頁在同一個 session 要改第 4 次，或同一個錯誤重試 2 次仍失敗 | 停，說明卡在哪裡 |

### 8.2 資料不足煞車

| ID | 條件 | 動作 |
|---|---|---|
| D1 | 想寫的事實在 raw/ 裡找不到來源 | 不寫成事實；需要背景知識時放在 `> [!background] unverified` 區塊，不得進 overview 與 rq 的缺口段 |
| D2 | 只有一個來源支持 | 標 `single-source`；不用 established、consensus、widely 這類字 |
| D3 | 只有 vendor-claim、news 或 rumor | 寫成「X 宣稱」或「據 Y 報導」；不當效能事實用 |
| D4 | 原檔讀不完整（付費牆、掃描檔、只有摘要） | 標 `read_depth` 與 `partial-read`；不引用沒讀到的細節；列入審查 |
| D5 | Query 時 wiki 不足以回答 | 直接說「wiki 目前資料不足」，列出缺什麼、建議找哪類來源，問你要不要找 |
| D6 | 數字缺條件（硬體、解析度、資料集） | 標 `conditions-unknown`；條件不同的數字不放在同一欄直接比較 |
| D7 | `as_of` 超過 6 個月 | 標 `stale`；不當現況引用 |
| D8 | 新舊來源衝突 | 不覆蓋，兩者並列並標 contradiction，等你判斷 |

### 8.3 範圍煞車
- S1 來源和 6 個步驟、3 個研究問題、平台與市場主題都無關：只寫最小來源頁並標 `out-of-scope`，或問你要不要跳過。
- S2 內容屬於「暫不做」：標 `deferred`，不展開 concept 頁。
- S3 你要的東西不屬於 wiki（寫程式、寫論文正文）：提醒你，問要不要改用其他工具。

### 8.4 煞車時怎麼做
1. 把手上的頁寫完整，不留半寫的頁。
2. 在 log.md 加 `## [日期] brake | 煞車 ID：原因`。
3. 回報四件事：哪個煞車、已完成什麼、還剩什麼、繼續大概還要多少（頁數、查詢次數）。
4. 等你回覆；你同意之前不繼續那件事。

## 9. 審查

### 9.1 自我檢查（每篇 ingest 結束前）
- [ ] 來源頁 frontmatter 齊全，`evidence` 與 `read_depth` 正確
- [ ] 每個主張都有頁碼或段落，以及證據等級
- [ ] 數字附條件
- [ ] 至少對應一個步驟、研究問題或平台主題，或已標 `out-of-scope`
- [ ] 推論已和事實分開
- [ ] 衝突已標記
- [ ] index.md 與 log.md 已更新
- [ ] 沒有未處理的煞車

### 9.2 批次審查清單
檔名 `wiki/review/YYYY-MM-DD-batch-N.md`，內容依序是：
1. 處理了哪些來源，各自的 `read_depth`
2. 新增與修改的頁
3. 重要的新主張，附證據等級
4. 衝突
5. 跳過或只讀一部分的來源
6. 需要你決定的事
7. 這批的 commit hash（退回時用）

你看完回覆「approve batch-N」或指出要改的地方；agent 再把相關頁改成 `review: approved`。

### 9.3 審查閘門
overview.md 的「Current position」段與 rq 頁的「Gap」段，只能引用 `review: approved` 的來源頁。
這是批次模式的安全網：錯誤在你審查前不會擴散到論文的主要論點。

### 9.4 定期審查
- 每 ingest 10 篇，或寫論文某一章前，跑一次 lint。
- 要寫進論文的關鍵引用，可以再用 `17_citation_abstract_verifier` skill 對一次原文摘要。

## 10. 完成標準（做到就停，不再擴寫）

| 操作 | 完成時 |
|---|---|
| Ingest 單篇 | §9.1 全部打勾，並回報改了哪些檔 |
| Ingest 批次 | 每篇已完成或已標記跳過；審查清單已產生；對話中有一段摘要 |
| Query | 有引用的回答；資料不足處已標出；問過要不要存檔 |
| Lint | 報告已產生；機械性修正已做；內容修改已列為建議 |
| 修改本檔 | 你同意的修改已寫入；log.md 有 `schema` 紀錄 |

Wiki 里程碑
- M1 可用：前 5 篇來源已 ingest 並通過審查；index、log、overview 都有在更新。
- M2 覆蓋：6 個步驟各有 3 個以上來源，其中至少 1 篇 peer-reviewed；3 個研究問題各有 3 個以上相關來源；Quest、Android XR、Vision Pro、Snap 的平台頁 `as_of` 都在 6 個月內。
- M3 可寫論文：每個研究問題都能從 wiki 產生一份 related work 大綱，每句連到 approved 來源；overview 寫出每個研究問題的缺口，各有 2 個以上來源支持。

## 11. 停止條件（整個主題或專案層級）

- 閱讀飽和：某步驟或研究問題連續 3 個新來源都沒有新主張，就標 `saturated`，建議停止找這個主題的來源，轉向覆蓋表上的缺口。
- 審查積壓：`review: pending` 的來源超過 10 篇，就暫停新的批次 ingest，直到你審完。
- 專案檢查點：私人內容，不公開（本機另存於 .private/checkpoints.md，不進 git）。

## 12. 修改本檔

- 本檔由你和 agent 一起演化。agent 覺得某條規則不好用時，引用條目編號、附上理由提出修改；你同意才寫入。
- 每次修改都更新版本號與日期，並在 log.md 加 `## [日期] schema | 改了什麼`。

## 13. 待決事項

- 自己的實驗數據與會議筆記要不要進 wiki（目前不收）。
- 論文最後用英文還是中文寫。
- 來源超過約 100 篇時，要不要加搜尋工具（例如 qmd）。
- 要不要加遠端備份（例如私人 GitHub repo）。目前只有本機；要 push 前先確認 raw/ 的文章剪輯能不能公開或要不要排除。
- Obsidian 的附件資料夾是否設為 `raw/assets/`。
