---
type: pipeline
id: step-1-segment
rq: [rq2-stability]
sources: 3
updated: 2026-11-22
---

# Step 1 — Segment: find the object

Scope (AGENTS.md §2): image segmentation of the target object and walls.
Current prototype (background, not evidence): Repaint, click-to-segment with MediaPipe.

## Methods in the literature
| Method | Source | Speed and conditions | Fits MVP-1? |
|---|---|---|---|
| Gesture-marked key points as prompts for MobileSAM | [[2025-hu-thing2reality]], pp. 5–6 | Desktop RTX 4070 Ti; VR controller input | Yes as an idea (replace gestures with a tap) |
| Region-of-interest detection as a DR stage (none, manual, automatic) | [[2017-mori-diminished-reality-survey]], pp. 3–4, 6 | Survey classification | Yes: MVP-1 uses manual (click) selection |
| No segmentation; named as future work | [[2018-lindlbauer-remixed-reality]], p. 10 | — | Shows the step is needed |

## What is solved

## Gap
Only `review: approved` sources here.

Not a gap. Prompt-based segmentation is available: MobileSAM prompted by gesture-marked points works inside an XR system ([[2025-hu-thing2reality]], pp. 5–6), and region-of-interest detection is a standard DR stage ([[2017-mori-diminished-reality-survey]], pp. 3–4). Remixed Reality had no segmentation and named it as future work ([[2018-lindlbauer-remixed-reality]], p. 10). The open part is keeping the mask stable over frames; see [[step-5-stability]].

## Sources
- [[2025-hu-thing2reality]]
- [[2017-mori-diminished-reality-survey]]
- [[2018-lindlbauer-remixed-reality]]

## 中文說明
- 找出物體：影像分割，目前用 Repaint（MediaPipe）點選分割。
- 這一步不是缺口：SAM 類的提示式分割已經能在 XR 系統裡用（Thing2Reality）。
- 真正的問題是遮罩在連續畫面中穩不穩，屬於 step-5。
