---
type: source
title: "Shader Lamps: Animating Real Objects With Image-Based Illumination"
authors: [Ramesh Raskar, Greg Welch, Kok-Lim Low, Deepak Bandyopadhyay]
year: 2001
venue: "Eurographics Workshop on Rendering 2001 (file is MERL technical report TR2001-21)"
evidence: peer-reviewed
raw: "raw/TR2001-21.pdf"
url: ""
doi: ""
read_depth: partial
pipeline: [step-4-composite, step-2-locate, step-6-control]
rq: [rq2-stability]
topics: []
as_of:
ingested: 2026-11-22
updated: 2026-11-22
review: approved
flags: [partial-read]
---

# Shader Lamps: Animating Real Objects With Image-Based Illumination (Raskar et al., 2001)

Read: abstract, introduction, previous work, illumination process, alignment and intensity correction (PDF pp. 1–7), limitations, applications, conclusion (pp. 9–10). Skipped: the multi-projector feathering algorithm details (pp. 7–8). Page numbers below are PDF pages.

## Summary
Shader Lamps replace a physical object's colour, texture and material with a neutral (white) object plus projected imagery, so the object shows its original or a new appearance. Projectors become "lamps" that carry the visual properties. The paper gives a radiance adjustment equation for how bright each projector pixel must be, a calibration method to register projectors to the object, and a way to blend several projectors around self-shadowing objects.

## Key claims
- Core idea: replace a physical object with a neutral object plus projected imagery that reproduces the original or an alternative appearance directly on it. (p. 4) `peer-reviewed`
- Beyond textures (the diffuse component), the method can reproduce "virtually any BRDF appearance"; with a tracked viewer, view-dependent effects such as specular highlights are possible. (pp. 5, 6)
- Radiance adjustment: projector pixel intensity is set from the desired radiance, distance and angle to the surface, and the surface's diffuse reflectance; it works only while the neutral surface's reflectance is non-zero, and is bounded by the projector's brightness, dynamic range and resolution. (p. 6, Eq. 4)
- Registration: fiducials with known 3D positions give a 3×4 projection matrix, decomposed into the projector's intrinsic and extrinsic parameters. Surfaces at more than 60° to the projector are not lit. (p. 7)
- Users can author appearance interactively by "painting" on the physical object. (p. 7)
- Limitations: depends on a neutral surface and controlled dark ambient lighting; secondary scattering cannot be fully avoided; projector black level and depth of field limit quality; shadows cast by users are "very disturbing". (p. 9)
- With head tracking, a clay vase can appear to be made of metal or plastic. (p. 9)

## Numbers and conditions
| Metric | Value | Conditions | Page |
|---|---|---|---|
| Max angle of surface to projector that is lit | 60° | design choice to limit oblique sampling | 7 |

## Relevance to this thesis
- [[appearance-editing-of-real-objects]], [[step-4-composite]]: the classic answer to "change how a real object looks", with projectors instead of a screen. Positioning reference for the thesis.
- [[rq2-stability]]: shows that appearance editing depends on ambient light; projection needs a dark room, which the phone approach avoids.
- [[step-6-control]]: painting directly on the object is an early form of in-place style control.

> [!inference] Our reading
> Shader Lamps change the object's appearance for everyone in the room and need no headset, but need a neutral surface, a dark room, and a 3D model. Phone video see-through trades those for a screen. This contrast is useful for explaining the design space.

## Links and contradictions
- Related: [[2018-lindlbauer-remixed-reality]] (cites Shader Lamps as spatial AR that changes appearance), [[2021-itoh-ost-hmd-survey]] (spatial AR needs geometric and radiometric alignment).
- No contradictions.

## 中文說明
- 經典研究：把真實物體換成白色的中性物體，再用投影機把原本或新的外觀「打」上去，投影機就像會上色的燈。
- 方法包括計算每個投影像素該多亮（radiance adjustment）、用標記點校準投影機位置、多台投影機的接縫處理。
- 限制：需要白色表面和暗的環境光；使用者的影子會擋住投影。
- 對本論文：這是「改變真實物體外觀」最早的代表，適合用來在簡報裡說明這個問題不是新的，只是做法在變。
