---
type: pipeline
id: step-4-composite
rq: [rq2-stability]
sources: 4
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
| Shader Lamps: radiance adjustment of projector pixels on a neutral object | [[2001-raskar-shader-lamps]], pp. 4–7, 9 | Needs neutral surface and dark ambient light | No; positioning reference |
| Remixed Reality: edit appearance of a live 3D reconstruction | [[2018-lindlbauer-remixed-reality]], pp. 1–3, 7 | Up to 100 fps render; eight Kinects | No; positioning reference |
| DR composition: homography for planar regions, alpha blending (cheap) or Poisson blending (costly) at seams | [[2017-mori-diminished-reality-survey]], pp. 7–8 | Survey classification | Yes: matches MVP-1's quad warp and blending |

Concepts: [[appearance-editing-of-real-objects]], [[diminished-reality]]

## What is solved
- Compositing in camera-image space is the easier route to visual coherence ([[2021-itoh-ost-hmd-survey]], p. 2).

## Gap
Only `review: approved` sources here.

Tentative gap (4 sources). Three routes to changing a real object's appearance exist: projection ([[2001-raskar-shader-lamps]]), editing a live 3D reconstruction ([[2018-lindlbauer-remixed-reality]]), and DR "replace" in video see-through ([[2017-mori-diminished-reality-survey]], p. 2). In the sources read, the new appearance is authored or pre-made, never generated from a style description. Video see-through is the easier route to coherence ([[2021-itoh-ost-hmd-survey]], p. 2), and DR on optical see-through is barely explored ([[2017-mori-diminished-reality-survey]], p. 10). See [[appearance-editing-of-real-objects]].

## Sources
- [[2021-itoh-ost-hmd-survey]] (partial read)
- [[2001-raskar-shader-lamps]]
- [[2018-lindlbauer-remixed-reality]]
- [[2017-mori-diminished-reality-survey]]
- Background only: [[2025-scrivener-intro-xr-book]] (Ch. 3 on combining real images and virtual objects, not read)

## 中文說明
- 貼回去：透視變換、遮罩、混色、光線。
- Itoh 指出手機這類影像透視（VST）在相機畫面裡合成，比較容易一致；OST 眼鏡無法完全控制光線。
- 改變真實外觀有三條路：投影、即時重建、影像透視合成（DR 的 replace）；MVP-1 屬於第三條。
- 暫定缺口：讀過的來源中，新外觀都是手動做好或預先準備的，沒有依風格描述即時生成。
