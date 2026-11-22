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

## Sources
- [[2025-hu-thing2reality]] (pending)
- [[2017-mori-diminished-reality-survey]] (pending)
- [[2018-lindlbauer-remixed-reality]] (pending)

## 中文說明
- 找出物體：影像分割，目前用 Repaint（MediaPipe）點選分割。
- 尚無來源。
