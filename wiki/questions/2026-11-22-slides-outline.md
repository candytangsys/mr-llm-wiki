---
type: question
asked: 2026-11-22
updated: 2026-11-22
review: pending
sources: [2001-raskar-shader-lamps, 2017-mori-diminished-reality-survey, 2018-lindlbauer-remixed-reality, 2021-itoh-ost-hmd-survey, 2024-pan-ctgan, 2025-hu-thing2reality, 2025-ning-genai-xr-review]
---

# Teaching slides outline — 「用 AI 改造你眼前的世界：MR 外觀改造入門」

Purpose: outline for a teaching HTML deck built only from this wiki, for classmates new to the topic. Slide text will be in Traditional Chinese with English terms. Each slide lists its learning goal and the wiki pages it may draw on; nothing outside those pages goes on a slide.

Query step: read [[index]], then [[overview]], the three concept pages, six pipeline hubs, three RQ hubs (13 pages; over the B7 limit of 10, see the check log below).

## Outline

| # | 標題 | 學習目標（看完這頁能…） | 依據的 wiki 頁 |
|---|---|---|---|
| 1 | 封面：用 AI 改造你眼前的世界 | — | [[overview]] |
| 2 | 今天要學的三件事＋名詞小抄 | 知道本簡報的目標；先認識 MR、VST、OST、DR 四個詞 | [[optical-vs-video-see-through]], [[diminished-reality]] |
| 3 | 從「加東西」到「改東西」 | 分辨 AR（加入虛擬物件）和 DR（隱藏、替換真實物件） | [[diminished-reality]]; [[2017-mori-diminished-reality-survey]] pp. 1–2 |
| 4 | 你是怎麼「看到」混合實境的？ | 說出 VST、OST、投影三種顯示方式的差別 | [[optical-vs-video-see-through]]; [[2021-itoh-ost-hmd-survey]] pp. 2–3 |
| 5 | 為什麼先用手機做？ | 解釋 VST 在影像中合成較容易、OST 無法完全控制光線 | [[2021-itoh-ost-hmd-survey]] pp. 2, 27–28; [[2017-mori-diminished-reality-survey]] pp. 3, 10 |
| 6 | 路線一：用投影改外觀（Shader Lamps） | 說出投影法怎麼運作，以及為何需要暗房 | [[2001-raskar-shader-lamps]] pp. 4, 6, 9 |
| 7 | 路線二：重建整個房間再編輯（Remixed Reality） | 說出重建法能做的四類操作與代價 | [[2018-lindlbauer-remixed-reality]] pp. 1, 3, 7, 9 |
| 8 | 路線三：在畫面裡替換（DR 的 replace） | 說出 DR 的五個步驟與三種不一致 | [[2017-mori-diminished-reality-survey]] pp. 1–4, 7–8 |
| 9 | 生成式 AI 走進 XR | 知道生成式 AI 目前在 XR 做什麼、MR 研究多少、速度到哪 | [[2025-ning-genai-xr-review]] pp. 10–11; [[2025-hu-thing2reality]] p. 6 |
| 10 | 還缺什麼？（暫定缺口） | 理解「依個人風格生成外觀、套回真實物體」目前讀過的文獻還沒做 | [[overview]] Current position; [[appearance-editing-of-real-objects]] |
| 11 | 六步驟 pipeline | 能依序說出分割、定位、生成、合成、穩定、控制，各舉一個方法 | pipeline hubs: [[step-1-segment]] … [[step-6-control]] |
| 12 | 三個還沒解決的問題 | 說出 RQ1 等待、RQ2 穩定、RQ3 風格控制各在問什麼 | [[rq1-waiting]], [[rq2-stability]], [[rq3-style-control]] |
| 13 | 小測驗（3 題） | 自我檢查是否理解 VST/OST、三條路線、pipeline | slides 4, 6–8, 11 |
| 14 | 重點回顧＋參考資料＋這份簡報怎麼做出來的 | 帶走三個重點；看到 8 篇來源；知道內容來自 LLM Wiki | [[index]], [[log]] |

## Check log (run at outline stage)

Check A — every slide traced to approved wiki pages:
- A1 Pass: all cited sources are `review: approved` (8 of 8).
- A2 Issue → fixed: slide 10's gap is tentative in the wiki ("holds for the sources read"). The slide must say 「就目前讀過的 8 篇文獻而言」, not 「沒有人做過」.
- A3 Issue → fixed: slide 11 could pull in MVP-1 details (Repaint 130 ms, koi pattern) from AGENTS.md §2, which is the vision draft, not a source. Rule: those may appear only labelled 「本研究的設計（非文獻）」, and no latency number is shown.
- A4 Issue → fixed: slide 9's counts (MR 1/26, natural language 20/26) come from one preprint review; the slide must name the source and say 「一篇系統性回顧統計」.
- A5 Pass: slide 9's "1–2 s" keeps its condition (desktop RTX 4070 Ti).

Check B — understandable for a newcomer:
- B1 Terms to define at first use: MR, VST, OST, DR, segmentation, diffusion model, homography, alpha blending, latency. Slide 2 carries a short glossary.
- B2 One idea per slide; at most 4 bullets; each slide ends with a one-line takeaway.
- B3 No formulas (Shader Lamps' Eq. 4 is out).

Budget note: the query step opened 13 wiki pages, over B7's 10. Accepted because a whole-deck outline needs every hub; recorded here as a brake event.

## 中文說明
- 14 頁大綱，每頁有學習目標和對應的 wiki 頁，簡報內容只能來自這些頁面。
- 在大綱階段先做了事實檢查：發現 3 個風險（缺口說得太滿、混入非文獻的 MVP-1 數字、單一來源的統計），都先改成標示方式。
- 新手可讀性：第 2 頁放名詞小抄、每頁一個重點、不放公式。
- 查詢時開了 13 頁，超過 10 頁的煞車門檻，已記錄。
