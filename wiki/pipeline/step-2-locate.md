---
type: pipeline
id: step-2-locate
rq: [rq2-stability]
sources: 4
updated: 2026-11-22
---

# Step 2 — Locate: know where it is

Scope (AGENTS.md §2): tracking, depth, plane detection.
Current prototype (background, not evidence): Scaffold XR plane detection; an orientation mirroring issue is still to be verified.

## Methods in the literature
| Method | Source | Speed and conditions | Fits MVP-1? |
|---|---|---|---|
| Eye-to-display spatial calibration for OST headsets (e.g., SPAAM) | [[2021-itoh-ost-hmd-survey]], p. 10 (caption), p. 27 | Not read | No: OST-only; MVP-1 is a phone |
| Scene tracking for DR: positioning sensors, vSLAM, and others | [[2017-mori-diminished-reality-survey]], p. 4 | Survey classification | Yes: vSLAM-style tracking is what phones provide |
| Eight fixed depth cameras reconstructing the room | [[2018-lindlbauer-remixed-reality]], pp. 4, 7 | Room about 4 × 5 m; ~30 fps capture | No: needs installed cameras |
| Projector calibration from fiducials (3×4 projection matrix) | [[2001-raskar-shader-lamps]], p. 7 | Static object with known 3D model | No: projection setup |

## What is solved
Nothing for phone-based tracking yet. For OST headsets, continuous (re)calibration is still described as challenging ([[2021-itoh-ost-hmd-survey]], p. 27).

## Gap
Only `review: approved` sources here.

No gap statement yet. The one approved source covers OST headsets only, where usable continuous recalibration is still open ([[2021-itoh-ost-hmd-survey]], p. 27; partial read, single-source). Nothing approved on phone tracking, depth, or plane detection.

## Sources
- [[2021-itoh-ost-hmd-survey]] (partial read)
- [[2017-mori-diminished-reality-survey]] (pending)
- [[2018-lindlbauer-remixed-reality]] (pending)
- [[2001-raskar-shader-lamps]] (pending)

## 中文說明
- 知道它在哪：追蹤、深度、平面偵測。
- 目前只有 Itoh 的 OST 頭戴校準內容，跟手機版 MVP-1 不太相關。
- 手機追蹤、深度、WebXR 平面偵測都還沒有來源。
