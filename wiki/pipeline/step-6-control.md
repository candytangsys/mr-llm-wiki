---
type: pipeline
id: step-6-control
rq: [rq3-style-control]
sources: 4
updated: 2026-11-22
---

# Step 6 — Control: how the user gives instructions

Scope (AGENTS.md §2): text prompts and option choices.
Current prototype (background, not evidence): partial.

## Methods in the literature
| Method | Source | Input type | Fits MVP-1? |
|---|---|---|---|
| Natural-language input (voice or text) to generative AI in XR, 20 of 26 studies | [[2025-ning-genai-xr-review]], p. 11 | Text, speech | Yes |
| Image input, 9 of 26 studies | [[2025-ning-genai-xr-review]], p. 11 | Image | Yes |
| Style image plus segmentation map as separate conditions | [[2024-pan-ctgan]], pp. 3–4 | Image (style), map (structure) | As a design idea |
| Gesture marking to select an object; text- or image-conditioned generation | [[2025-hu-thing2reality]], pp. 5–6 | Gesture, text, image | Yes as an idea |
| Painting appearance directly onto the physical object | [[2001-raskar-shader-lamps]], p. 7 | Direct painting | Idea for in-place editing |

## What is solved

## Gap
Only `review: approved` sources here.

No gap statement yet. The approved evidence is input-mode counts from one preprint review ([[2025-ning-genai-xr-review]], p. 11) and one method that uses a style image as input ([[2024-pan-ctgan]]). See [[rq3-style-control]].

## Sources
- [[2025-ning-genai-xr-review]]
- [[2024-pan-ctgan]]
- [[2025-hu-thing2reality]]
- [[2001-raskar-shader-lamps]]

## 中文說明
- 使用者怎麼下指令：文字、選項。
- 生成式 XR 研究裡自然語言輸入最多（20/26），圖片輸入 9 篇。
- CTGAN 用「風格圖片」而不是文字來指定外觀，可以作為選項式介面的參考。
