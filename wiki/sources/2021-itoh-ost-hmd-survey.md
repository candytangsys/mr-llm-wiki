---
type: source
title: "Towards Indistinguishable Augmented Reality: A Survey on Optical See-Through Head-Mounted Displays"
authors: [Yuta Itoh, Tobias Langlotz, Jonathan Sutton, Alexander Plopski]
year: 2021
venue: "ACM Computing Surveys (the file is the accepted preprint; volume, article number and DOI are placeholders)"
evidence: peer-reviewed
raw: "raw/papers/ItohACMCSURV2021.pdf"
url: ""
doi: "TODO"
read_depth: partial
pipeline: [step-2-locate, step-4-composite, step-5-stability]
rq: [rq2-stability, rq1-waiting]
topics: []
as_of:
ingested: 2026-11-22
updated: 2026-11-22
review: approved
flags: [partial-read, secondhand]
---

# Towards Indistinguishable AR: A Survey on Optical See-Through HMDs (Itoh et al., 2021)

Read: abstract and introduction (pp. 1–3), discussion and conclusion (pp. 27–29), figure captions. Not read: sections 2–6 (pp. 3–27), which hold the details on calibration, latency, colour, accommodation, and occlusion.

## Summary
A survey of what it would take for optical see-through head-mounted displays (OST-HMDs) to show virtual content indistinguishable from reality. It defines requirements from human perception, then reviews work on three challenges: spatial realism (calibration, registration), temporal realism (latency), and visual realism (colour, accommodation, occlusion, resolution).

## Key claims
- Video see-through (phone AR, VST headsets) merges virtual and real in camera-image space, which makes visual coherence easier; the cost is that the user never sees the real world directly. (p. 2) `peer-reviewed`
- Spatial AR (projection mapping) is a third route; it needs geometric and radiometric alignment of projectors with their surroundings. (p. 2)
- OST displays show the real world at full fidelity, but a visually coherent experience with them is generally considered more challenging. (p. 3)
- Per this survey, earlier work found low-fidelity displays can still convince, e.g., by simplifying the appearance of the physical world (Fischer et al.; Regenbrecht et al.; refs 34, 142, 143). (p. 3) `secondhand`
- Few works address latency, colour representation, or resolution, and many techniques exist only as benchtop prototypes. (p. 27)
- Temporal realism, and latency in particular, is rarely addressed in AR research. (p. 27)
- A usable continuous (re)calibration remains challenging; eye tracking looks key. (p. 27)
- The inability to fully control light in an OST-HMD is a core obstacle to visual realism: existing approaches either adapt the displayed image to incoming light (colour blending) or control incoming light (occlusion); none do both. Per-pixel light-attenuation displays are one direction. (pp. 27–28)
- Not a systematic review; all reported data come from the original papers. (p. 28)

## Numbers and conditions
No numbers in the sections read.

## Relevance to this thesis
- [[step-4-composite]], [[optical-vs-video-see-through]]: MVP-1 runs on a phone, which is video see-through, the easier case for coherent compositing.
- [[step-5-stability]], [[rq1-waiting]]: latency is under-addressed in AR research; agrees with [[2025-ning-genai-xr-review]].
- [[step-2-locate]], [[rq2-stability]]: spatial calibration and continuous recalibration are open problems for OST headsets.
- Reading list: the cited work on simplifying the real world's appearance (Fischer et al.; Regenbrecht et al.) is a close cousin of restyling reality.

> [!inference] Our reading
> The coverage check guessed that OST glasses cannot darken a real surface. The conclusion is consistent with that: OST-HMDs lack full control over light, and filtering incoming light needs special attenuation hardware still in research (pp. 27–28). For the headset version, restyling by darkening or replacing real appearance would be limited. Sections 6.1 (colour) and 6.3 (occlusion) hold the details and were not read.

## Links and contradictions
- Related: [[2025-ning-genai-xr-review]].
- No contradictions yet.

## 中文說明
- 光學透視頭戴顯示器（OST-HMD）的綜述，ACM Computing Surveys（檔案是接受後的預印本）；只讀了摘要、引言、結論和圖說。
- 手機這類影像透視（VST）在相機畫面裡合成，比較容易做到視覺一致；OST 能看到最真實的世界，但一致性更難。
- latency 在 AR 研究中很少被處理，跟 Ning 的回顧一致。
- OST 無法完全控制光線（只能加光或另外用硬體濾光），所以未來頭戴版的「改造外觀」會受限；MVP-1 用手機是比較好做的路線。
- 文中引用的 Fischer、Regenbrecht 等「簡化真實世界外觀」的研究，跟本論文最接近，值得找原文。
