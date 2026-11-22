---
type: pipeline
id: step-3-generate
rq: [rq1-waiting, rq3-style-control]
sources: 3
updated: 2026-11-22
---

# Step 3 — Generate: a new appearance from a style description

Scope (AGENTS.md §2): diffusion models that generate the new appearance from the user's style description.
Current prototype (background, not evidence): not started. MVP-1 uses a pre-generated koi pattern instead of live generation.

## Methods in the literature
| Method | Source | Speed and conditions | Fits MVP-1? |
|---|---|---|---|
| Diffusion models in GenAI-XR systems (14 of 26 studies) | [[2025-ning-genai-xr-review]], p. 10 | Not reported in the review | Unclear: used for virtual content, not real-object appearance |
| CTGAN: texture generation conditioned on a segmentation map and a style image (StyleGAN2-ADA) | [[2024-pan-ctgan]], pp. 3–6 | Inference time not reported; trained on 128×128 images, one V100 | No as a method (virtual 3D models, per-category training); yes as a design idea |
| Segment, then multi-view diffusion, then Large Gaussian Model to a 3D object | [[2025-hu-thing2reality]], pp. 2, 6 | 3D object within 1–2 s on RTX 4070 Ti desktop | Partly: creates a virtual copy, not an in-place restyle |

## What is solved
- Style-image-conditioned texture generation for one object category, with structure and style controlled separately ([[2024-pan-ctgan]]).

## Gap
Only `review: approved` sources here.

Tentative gap (3 sources). The approved generative systems create virtual content ([[2025-ning-genai-xr-review]], p. 13; [[2024-pan-ctgan]], p. 1) or new virtual copies of real objects ([[2025-hu-thing2reality]], p. 2). None applies a generated appearance in place on the real object. This is a statement about the sources read, not yet about the whole field; a targeted search (e.g., AR stylization, generative texture on real objects) would make it stronger.

## Sources
- [[2025-ning-genai-xr-review]]
- [[2024-pan-ctgan]]
- [[2025-hu-thing2reality]]

## 中文說明
- 生成新外觀：擴散模型依風格描述生成。
- 三個來源：Ning 的回顧（diffusion 是生成式 XR 最常用的模型）、CTGAN（分割圖＋風格圖片生成貼圖）、Thing2Reality（分割後 1–2 秒生成 3D 物件）。
- 暫定缺口：它們都在生成虛擬內容或虛擬複製品，沒有一個把生成的外觀直接套在真實物體上。
