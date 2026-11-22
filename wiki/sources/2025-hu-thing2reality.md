---
type: source
title: "Thing2Reality: Enabling Spontaneous Creation of 3D Objects from 2D Content using Generative AI in XR Meetings"
authors: [Erzhen Hu, Mingyi Li, Jungtaek Hong, Xun Qian, Alex Olwal, David Kim, Seongkook Heo, Ruofei Du]
year: 2025
venue: "UIST 2025"
evidence: peer-reviewed
raw: "raw/3746059.3747621.pdf"
url: ""
doi: "10.1145/3746059.3747621"
read_depth: partial
pipeline: [step-1-segment, step-3-generate, step-6-control]
rq: [rq1-waiting, rq3-style-control]
topics: []
as_of:
ingested: 2026-11-22
updated: 2026-11-22
review: pending
flags: [partial-read]
---

# Thing2Reality (Hu et al., UIST 2025)

Read: abstract, introduction (pp. 1–2), segmentation and system setup (pp. 5–6), limitations and conclusion (pp. 12–13). Skipped: related work details, study procedures and results (pp. 3–4, 7–12).

## Summary
Thing2Reality is an XR meeting system that turns 2D content (a video feed of a physical object, a web image) into shared 3D objects. The user marks an object, MobileSAM segments it, multi-view diffusion models render it from several views, and a Large Gaussian Model fuses the views into a 3D Gaussian object that people can move and discuss. Two user studies (N=12, N=18) explore how 2D and 3D objects shape collaboration.

## Key claims
- Pipeline: segment content from any source, generate multi-view renderings with conditioned multi-view diffusion models, fuse them into 3D Gaussians for manipulation. (p. 2) `peer-reviewed`
- Segmentation uses continuous marking gestures with a VR controller to extract three key points, which prompt SAM; this avoids precise multi-click input. (p. 5)
- The orthogonal views appear first in a pie menu, then the 3D Gaussian object appears "within 1-2 seconds". (p. 6, figure caption)
- System setup: Intel i7-13700K, NVIDIA RTX 4070 Ti; MobileSAM, text-conditioned and image-conditioned multi-view diffusion, Large Gaussian Models. (p. 6)
- User studies: a preliminary study (N=12) on digital vs physical sources, an exploratory study (N=18) on collaboration patterns. (p. 2)
- Limitations: generation may introduce unacceptable inaccuracies where precision matters (e.g., medical); abstract concepts are hard to visualise; higher fidelity costs more rendering time. (pp. 12–13)

## Numbers and conditions
| Metric | Value | Conditions | Page |
|---|---|---|---|
| Time until 3D Gaussian object appears | 1–2 s | i7-13700K + RTX 4070 Ti desktop; after segmentation; figure caption, method of timing not stated | 6 |
| Study sizes | N=12, N=18 | preliminary and exploratory studies | 2 |

## Relevance to this thesis
- [[step-3-generate]]: a recent, working pipeline from a segmented real object to generated content within seconds on a desktop GPU.
- [[step-1-segment]], [[step-6-control]]: gesture-marked prompts for SAM are a concrete way to select the object to restyle.
- [[rq1-waiting]]: the system shows intermediate multi-view renderings before the final 3D object, a form of progressive preview while generation finishes.
- [[rq3-style-control]]: both text and image can condition generation.

> [!inference] Our reading
> Thing2Reality creates new virtual copies of real objects rather than changing the real object in place, so it does not close the thesis gap, but its segment-then-generate pipeline and its "show partial results first" behaviour are directly reusable ideas.

## Links and contradictions
- Related: [[2025-ning-genai-xr-review]] (dynamic content generation triggered by user input), [[2024-pan-ctgan]] (image-conditioned generation).
- No contradictions.

## 中文說明
- UIST 2025 論文：在 XR 會議中，把畫面上的 2D 內容（實體物品的視訊畫面、網路圖片）即時變成可以操作的 3D 物件。
- 流程：手勢標記 → MobileSAM 分割 → multi-view diffusion 產生多視角圖 → Large Gaussian Model 合成 3D Gaussian。
- 多視角圖會先顯示，1–2 秒內出現 3D 物件（桌機 RTX 4070 Ti）。
- 對本論文：「分割再生成」的流程可借用；「先給中間結果」正好是 RQ1（等待時呈現什麼）的一個例子。
- 但它是做出新的虛擬複製品，不是改變真實物體本身的外觀。
