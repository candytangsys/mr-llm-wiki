---
type: review
kind: slides-check
updated: 2026-11-22
---

# Slides check record — run 1 (2026-11-22)

Deck: `slides/index.html`, 14 slides, built from [[2026-11-22-slides-outline]]. This is the execution record for the slide loop: query → outline → check A/B (at outline stage) → write → check A → HTML → check C → fix → re-check.

## Check A at outline stage (before any slide text)
| # | Finding | Action |
|---|---|---|
| A2 | Slide 10 gap would read as "nobody has done this"; the wiki only says "holds for the sources read" | Wording rule: 「就目前讀過的 8 篇文獻而言」, labelled 暫定 |
| A3 | Slide 11 could pull MVP-1 numbers (Repaint 130 ms) from the vision draft, which is not a source | Labelled 「本研究的設計（非文獻）」; no numbers shown |
| A4 | Slide 9 counts (MR 1/26) come from one preprint | Slide names it as 「一篇系統性回顧統計…預印本」 |

## Check A on the finished HTML (script)
- 15 wiki paths cited on slides: all exist.
- 18 numeric or specific claims (8 Kinects, 4 × 5 m, 100 fps, 30 fps, 26 studies, VR 10 / AR 8 / MR 1, 20, 14, 1–2 s, RTX 4070 Ti, 2023–2025 Q1, metal or plastic, dark ambient, homography, alpha blending, Poisson, geometric/photometric/temporal, OST DR unexplored): all found in wiki source pages.
- Weakness found in the checker itself: "26 studies" matched [[2024-pan-ctgan]] first ("9 of 26"), not the cited [[2025-ning-genai-xr-review]]. The claim was right, but the script would have passed a claim even if only an unrelated page contained the number. Fix for next run: match each claim only against the source page cited on the same slide.

## Check B (newcomer readability)
- Glossary on slide 2 defines MR, VST, OST, DR, segmentation, latency; homography and alpha blending are explained in place on slide 8.
- Every content slide has at most 4 bullets and one takeaway line. No formulas.

## Check C (presentation, in the browser)
| Test | Result |
|---|---|
| Console errors | none |
| Static `data:` preview | key sequence interrupted because each slide change rewrites the URL hash; switched to a local HTTP server (`.claude/launch.json`) |
| Jump to a slide by changing the hash (e.g., `#8`) | **Bug**: URL changed but slide 2 stayed on screen; no `hashchange` handler. Fixed in the HTML, re-tested: all 14 slides reachable |
| Desktop 1280 × 800 | all 14 slides fit; no horizontal scroll |
| Mobile 375 × 812 | no horizontal scroll; slides 2, 4, 10, 12 scroll inside the slide |
| Dark mode | renders correctly (screenshots) |

## Which node failed most in this run
The checks themselves surfaced problems at three nodes: wording at the outline (3 issues), the claim checker (too loose), and the HTML navigation (1 bug). Facts were never wrong; the risk was overstatement, which is why check A moved to the outline stage.

## 中文說明
- 大綱階段的事實檢查抓到 3 個「說得比證據強」的問題，在寫內容前就修正。
- 完成後用腳本核對 15 個路徑、18 個數字，全部在 wiki 找得到；但發現檢查腳本本身太寬鬆（應該只比對該頁標註的來源）。
- 瀏覽器檢查抓到一個翻頁 bug（直接改網址的頁碼不會跳頁），已修正並重測 14 頁。
- 桌機每頁完整顯示；手機無水平捲軸，4 頁需要在頁內捲動。

# Slides check record — run 2 (2026-11-22): motion design

Request: add five motion designs, each tied to an MR concept. Placed as labelled illustrations (「示意動畫，非真實系統畫面」), so no new factual claims enter the deck.

| Motion | Slide | MR concept | Implementation |
|---|---|---|---|
| Depth Interaction | 1 | depth perception | three SVG layers move by different amounts with the pointer; slow idle sway |
| Material Transformation | 3 | style transfer (DR replace) | pattern wiped across the laptop lid via an animated clip |
| Surface Recognition | 8 | target detection | lid outline traced with stroke-dashoffset, then tinted and labelled |
| Spatial Tracking | 11 | object tracking (step 2) | scene pans; a dashed tracking box follows with a slight lag |
| Spatial Anchoring | 12 | anchoring (RQ2) | anchored pattern moves with the scene; an unanchored copy stays on screen and separates |

Check C, run 2:
| Test | Result |
|---|---|
| Animations running | yes on all five slides (`getAnimations`), parallax variable changing, wipe transform sampled from 0 to 0.93 |
| Desktop 1280 × 800 | **Regression**: slides 8, 11, 12 overflowed by 32, 76, 20 px after adding demos. Capped demo heights (180 px; 145 px on slide 11; 120 px inside the RQ2 card); re-test: all 14 fit |
| Measurement error | one measurement ran while the pane width changed and the emulated size was cleared, giving false overflow of 350–410 px; re-measured after setting the size again |
| Mobile 375 × 812 | no horizontal scroll; demos stack under text, so 8 slides scroll inside the slide |
| Console errors | none |
| Reduced motion | CSS shows the final frame when the OS asks for reduced motion (not tested in the browser) |

Lesson for the loop: adding visuals is a change to node ⑦ (HTML) that can break ⑧ (layout) on slides that already passed, so check C must re-run on every slide, not only on the edited ones.
