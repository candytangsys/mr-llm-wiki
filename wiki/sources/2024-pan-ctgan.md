---
type: source
title: "CTGAN: Semantic-guided Conditional Texture Generator for 3D Shapes"
authors: [Yi-Ting Pan, Chai-Rong Lee, Shu-Ho Fan, Jheng-Wei Su, Jia-Bin Huang, Yung-Yu Chuang, Hung-Kuo Chu]
year: 2024
venue: "arXiv preprint, cs.CV, 2402.05728v1 (8 Feb 2024); ACM template with venue fields left blank"
evidence: preprint
raw: "raw/papers/2402.05728v1.pdf"
url: "https://arxiv.org/abs/2402.05728"
doi: ""
read_depth: full
pipeline: [step-3-generate, step-6-control]
rq: [rq3-style-control]
topics: []
as_of:
ingested: 2026-11-22
updated: 2026-11-22
review: approved
flags: [conditions-unknown]
---

# CTGAN: Semantic-guided Conditional Texture Generator for 3D Shapes (Pan et al., 2024)

## Summary
CTGAN generates texture maps for 3D shapes from two inputs: a semantic segmentation map, which fixes structure, and a reference style image, which sets appearance. It builds on StyleGAN2-ADA and splits the latent code into structure layers and style layers, each fed by its own encoder. On cars it reports large FID gains over Texture Fields and LTG.

## Key claims
- The latent code is split: the first n layers control structure (pose, shape, semantic parts), the rest control style. A coarse-to-fine structure encoder maps segmentation maps to the structure code; a pSp encoder maps the style image to the style code. (pp. 3–4, §4.2–4.3) `preprint`
- Textures are parameterised by projecting the 3D model onto N canonical views (six for cars) to make UV maps; segmentation maps are drawn by hand or with off-the-shelf methods. (p. 4, §4.1)
- Conditional setting, cars: FID 39.41, against 139.63 (Texture Fields) and 149.82 (LTG). (p. 6, Table 1)
- Conditional setting, faces: best FID (21.56) but not best KID or GIQA. (pp. 5–6, Table 1)
- Segmentation maps beat silhouettes as the structure input (FID 39.41 vs 42.86); the coarse-to-fine encoder beats a plain pSp encoder (39.41 vs 41.33). (p. 6, Table 2)
- The authors argue that text-prompt diffusion texturing (TEXTure, Text2Tex, Latent-NeRF) is not ideal when fine-grained control of semantics and structure is needed. This is their position; they do not compare against those methods. (p. 3)
- Limitations: self-occluding geometry and seams between views. (p. 7)

## Numbers and conditions
| Metric | Value | Conditions | Page |
|---|---|---|---|
| FID, cars, conditional | 39.41 | CompCars split 16,000/2,000/2,000; training images 128×128; trained 7 days on one NVIDIA V100 32 GB | 5, 6 |
| FID, faces, conditional | 21.56 | FFHQ split 65,747/64/3,000; same training setup | 5, 6 |
| Inference time | not reported | `conditions-unknown` | — |

## Relevance to this thesis
- [[rq3-style-control]]: a concrete pattern for separating "which part is where" (segmentation as structure) from "what it should look like" (style image).
- [[step-3-generate]]: style-image conditioning as an alternative to text prompts.
- [[step-6-control]]: the user's instruction is an image, not text.

> [!inference] Our reading
> In this thesis the structure input could come from segmenting the real object ([[step-1-segment]]) and the style from a reference image the user picks. But CTGAN works on virtual 3D models with UV maps, is trained per category (cars, faces), and reports no speed, so it is a design idea rather than a usable method. TEXTure and Text2Tex, cited in its related work, are the diffusion-era methods to read next.

## Links and contradictions
- Related: [[2025-ning-genai-xr-review]] (image input in 9 of 26 GenAI-XR studies).
- No contradictions yet.

## 中文說明
- 用「分割圖（結構）＋風格圖片（外觀）」兩個條件，替 3D 模型生成貼圖；基於 StyleGAN2-ADA，把 latent code 分成結構層和風格層。
- 車輛資料的 conditional FID 39.41，遠低於 Texture Fields（139.63）和 LTG（149.82）。
- 對 rq3：提供「結構和風格分開控制」的具體做法，而且風格用圖片而不是文字描述。
- 限制：只處理虛擬 3D 模型、每個類別各自訓練、沒有報告速度，不能直接用在即時改造真實物體。
- 預印本，venue 未填。
