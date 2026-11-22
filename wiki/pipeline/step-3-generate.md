---
type: pipeline
id: step-3-generate
rq: [rq1-waiting, rq3-style-control]
sources: 2
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

## What is solved
- Style-image-conditioned texture generation for one object category, with structure and style controlled separately ([[2024-pan-ctgan]]).

## Gap
Only `review: approved` sources here. (none approved yet)

## Sources
- [[2025-ning-genai-xr-review]]
- [[2024-pan-ctgan]]

## 中文說明
- 生成新外觀：擴散模型依風格描述生成。
- 目前有兩個來源：Ning 的回顧（diffusion 是生成式 XR 最常用的模型）和 CTGAN（分割圖＋風格圖片生成貼圖）。
- 兩者都在生成虛擬內容，沒有處理真實物體，也都沒有速度數據。
