---
type: concept
aliases: [real-object restyling, appearance editing, replace (DR), 外觀改造]
pipeline: [step-4-composite, step-1-segment, step-3-generate]
rq: [rq2-stability, rq3-style-control]
sources: 3
updated: 2026-11-22
flags: []
---

# Appearance editing of real objects

## Definition
Changing how a real, physical object looks to the user while it stays in place: new colour, texture, or material, or covering it with something else. Diminished reality calls covering a real object with virtual content "replace" ([[2017-mori-diminished-reality-survey]], p. 2). This is the core of this thesis.

## Approaches in the literature
| Approach | Sources | How the new look reaches the eye | Limits |
|---|---|---|---|
| Projection (spatial AR) | [[2001-raskar-shader-lamps]], pp. 4–9 | Projectors light a neutral object with the new appearance | Needs neutral surface, dark room, 3D model; user shadows |
| Live 3D reconstruction in VR | [[2018-lindlbauer-remixed-reality]], pp. 1–3, 7 | The room is rebuilt from depth cameras and re-rendered with edits | Eight depth cameras; visual quality limited by them |
| Video see-through compositing (DR "replace") | [[2017-mori-diminished-reality-survey]], pp. 2–3, 7–8 | Edited camera image on a screen | Geometric, photometric, temporal inconsistency |

## Relevance to this thesis
MVP-1 sits in the third row: a phone camera image, a segmented planar object, a perspective-warped pattern, and blending. What is new here is generating the appearance from the user's style with generative AI ([[step-3-generate]]) and keeping it stable ([[step-5-stability]]).

## Open problems
- Projection needs controlled lighting ([[2001-raskar-shader-lamps]], p. 9); reconstruction needs heavy infrastructure ([[2018-lindlbauer-remixed-reality]], p. 9); DR on OST displays is barely explored ([[2017-mori-diminished-reality-survey]], p. 10).

> [!inference]
> None of the three approaches generates the new appearance from a style description; that is where generative AI would enter. Needs a targeted search before it can be called a gap.

## 中文說明
- 定義：真實物體留在原地，但使用者看到的顏色、材質變了，或被別的東西蓋住；DR 領域稱為 replace。
- 三條路線：投影（Shader Lamps）、即時 3D 重建後重畫（Remixed Reality）、在相機畫面裡合成（DR，MVP-1 屬於這種）。
- 本論文的新意在於用生成式 AI 依個人風格產生外觀，並在移動中保持穩定。
