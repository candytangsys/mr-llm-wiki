---
type: pipeline
id: step-4-composite
rq: [rq2-stability]
sources: 1
updated: 2026-11-22
---

# Step 4 — Composite: put it back

Scope (AGENTS.md §2): perspective warp, masking, blending, lighting.
Current prototype (background, not evidence): simplified, Multiply blending. MVP-1 plan: take the mask's quadrilateral, warp the pattern onto it, clip with the mask, Multiply to keep shading, smooth the quadrilateral to reduce flicker.

Concept: [[optical-vs-video-see-through]]

## Methods in the literature
| Method | Source | Speed and conditions | Fits MVP-1? |
|---|---|---|---|
| Video see-through: merge in camera-image space | [[2021-itoh-ost-hmd-survey]], p. 2 | General statement | Yes: MVP-1 is a phone (VST) |
| OST colour blending compensation and occlusion handling | [[2021-itoh-ost-hmd-survey]], pp. 27–28 (sections 6.1, 6.3 not read) | Many are benchtop prototypes | No: OST-only |
| Spatial AR / projection mapping | [[2021-itoh-ost-hmd-survey]], p. 2 | Needs geometric and radiometric projector alignment | No for MVP-1; relevant prior work for positioning |

## What is solved
- Compositing in camera-image space is the easier route to visual coherence ([[2021-itoh-ost-hmd-survey]], p. 2).

## Gap
Only `review: approved` sources here.

No gap statement yet. Approved evidence says only that video see-through is the easier route to coherent compositing and that OST headsets cannot fully control light ([[2021-itoh-ost-hmd-survey]], pp. 2, 27–28; single-source). No approved source changes a real object's appearance in video.

## Sources
- [[2021-itoh-ost-hmd-survey]] (partial read)
- Background only: [[2025-scrivener-intro-xr-book]] (Ch. 3 on combining real images and virtual objects, not read)

## 中文說明
- 貼回去：透視變換、遮罩、混色、光線。
- Itoh 指出手機這類影像透視（VST）在相機畫面裡合成，比較容易一致；OST 眼鏡無法完全控制光線。
- 目前還沒有處理「在影像中改變真實物體外觀」的方法來源。
