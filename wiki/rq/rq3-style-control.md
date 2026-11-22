---
type: rq
id: rq3-style-control
pipeline: [step-3-generate, step-6-control]
sources: 2
updated: 2026-11-22
---

# RQ3 — How can the user control style precisely instead of by luck?

Question: how can the user steer the generated style precisely, rather than regenerating until something looks right?
Related steps: [[step-3-generate]], [[step-6-control]]

## Related work
| Approach | Source | Control type | Evidence |
|---|---|---|---|
| Separate structure (segmentation map) from style (reference image) in the latent code | [[2024-pan-ctgan]], pp. 3–4, 6 | Image plus map | preprint |
| Natural language as the dominant input in GenAI-XR; image input less common | [[2025-ning-genai-xr-review]], p. 11 | Text, speech, image | preprint |

## Gap
Only `review: approved` sources here.

Tentative, not yet a gap. Generative AI in XR mostly takes natural-language input: 20 of 26 studies, against 9 with image input ([[2025-ning-genai-xr-review]], p. 11; `single-source`, preprint). CTGAN's authors argue text prompts are not ideal for fine-grained control and use a style image instead ([[2024-pan-ctgan]], p. 3), but they do not test this against text-prompt methods. Diffusion-era control methods (ControlNet, IP-Adapter, StyleAligned) are needed before this becomes a gap statement.

## Candidate directions

> [!inference]
> CTGAN's split suggests one direction: let the real object's segmentation fix the structure and let the user control only style, through a reference image rather than text. Diffusion-era control methods (ControlNet, IP-Adapter, StyleAligned) are needed before this can be compared.

## Sources
- [[2024-pan-ctgan]]
- [[2025-ning-genai-xr-review]]

## 中文說明
- 如何讓使用者精確控制「風格」，而不是每次碰運氣。
- CTGAN 把「結構」和「風格」分開控制，風格用圖片指定，是目前最直接相關的做法。
- 生成式 XR 研究多用自然語言輸入，圖片輸入較少。
- 推論：真實物體的分割決定結構，使用者只控制風格；需要再讀 diffusion 時代的控制方法來比較。
