---
type: source
title: "When Generative Artificial Intelligence meets Extended Reality: A Systematic Review"
authors: [Xinyu Ning, Yan Zhuo, Xian Wang, Chan-In Devin Sio, Lik-Hang Lee]
year: 2025
venue: "arXiv preprint, cs.HC, 2511.03282v1 (5 Nov 2025)"
evidence: preprint
raw: "raw/papers/2511.03282v1.pdf"
url: "https://arxiv.org/abs/2511.03282"
doi: ""
read_depth: full
pipeline: [step-3-generate, step-5-stability, step-6-control]
rq: [rq1-waiting, rq3-style-control]
topics: []
as_of:
ingested: 2026-11-22
updated: 2026-11-22
review: pending
flags: [single-source, secondhand]
---

# When Generative AI meets Extended Reality: A Systematic Review (Ning et al., 2025)

## Summary
A PRISMA systematic review of generative AI used in XR systems, covering studies from 2023 to 2025 Q1. From 673 candidate records the authors kept 26 original studies and coded each by XR type, generative model, user input, and feedback cue. Most studies use generative AI to create virtual content (images, 3D models, text) in VR or AR. The authors name multimodal integration, latency, and standardisation as the main open problems.

## Key claims
- Search: IEEE Xplore, ACM DL, ScienceDirect, plus Google Scholar snowballing and arXiv; extraction in Feb and Apr 2025; 673 records, 637 after duplicates, 35 full texts, 26 included. (pp. 2–4, Fig. 1) `preprint`
- Included studies by year: 3 (2023), 15 (2024), 8 (2025 Q1). (p. 6, Fig. 2)
- Application domains: design 13, education and training 5, transmission 3, medical 3, architecture 2; commerce, gaming, traffic, cultural heritage 1 each. Studies can count in several domains. (pp. 7–8, Fig. 4)
- XR type: VR 10, AR 8, MR 1, not specified 8. (p. 10)
- Generative models: diffusion 14, LLM 9, GAN 5, transformer 4, VLM 3, Shap-E 2. (pp. 10–11)
- User input: natural language 20, image 9, pose 1, behaviour 1. Output: image or model generation in all but 4 studies; text 7; voice 5; motion and tactile 1. (p. 11)
- Two integration modes: object generation from preset parameters with indirect user input, and dynamic content generation triggered directly by user input (e.g., Dream Mesh, MS2Mesh-XR). (p. 13)
- Latency and stuttering: generative models need substantial compute; current work moves models to edge devices; compression and quantisation for the edge need more work. (p. 15, §4.3.2)
- AR pipelines with generative AI enable in-situ, user-driven object creation. (pp. 15–16, §4.3.4)
- Most evaluations are short-term lab studies; long-term, real-world testing is missing. (p. 18, §5.4)
- Per this review, BlendScape (Rajaram et al. 2024) blends physical or virtual backgrounds into AI-generated scenes for video conferencing, and SpaceBlender (Numan et al. 2024) blends several users' physical surroundings into one 3D space; a user study reported better comfort, navigability, and task coordination. (p. 19) `secondhand`
- The authors describe their sample as small. (p. 20)

## Numbers and conditions
| Metric | Value | Conditions | Page |
|---|---|---|---|
| Studies included | 26 | 2023 to 2025 Q1; English; original research using XR devices | 3, 5 |
| Studies using MR | 1 of 26 | authors' own coding | 10 |
| Natural-language input | 20 of 26 | authors' own coding | 11 |
| Diffusion models used | 14 of 26 | authors' own coding | 10 |

## Relevance to this thesis
- [[step-3-generate]]: diffusion is the most used model family in this literature, but for creating virtual content.
- [[step-5-stability]], [[rq1-waiting]]: names latency and stuttering as open problems; gives no latency numbers.
- [[step-6-control]], [[rq3-style-control]]: natural language is the dominant input; image input appears in 9 studies.
- Gap framing: only 1 of 26 studies is MR. Single preprint source, so it needs a second review (e.g., Hirzle et al. 2023) before going into the gap statement.

## Limitations
- Stated by the authors: small sample (p. 20); Google Scholar and arXiv used alongside the main databases, with manual screening instead of tools such as ROBIS (p. 4); search stops at 2025 Q1 (p. 6).

> [!inference] Our reading
> None of the systems the review describes changes the appearance of a real object; §4.3.4 "AI-enabled virtuality in physical worlds" is about placing new virtual objects. If this holds after reading the primary studies, it supports the thesis gap, but this review alone cannot show it.
> The XR-type counts sum to 27 for 26 studies, probably because some studies count twice; treat the counts as approximate.

## Links and contradictions
- Related: [[2021-itoh-ost-hmd-survey]] (both describe latency as under-addressed).
- No contradictions yet.

## 中文說明
- PRISMA 系統性回顧（預印本），整理 2023 到 2025 Q1 共 26 篇「生成式 AI＋XR」研究。
- 多數研究用生成式 AI 產生虛擬內容（圖片、3D 模型、文字）；MR 只有 1 篇，natural language 輸入 20 篇，diffusion 14 篇。
- 作者列出的缺口：多模態整合、latency 與 stuttering、系統標準化；評估多為短期實驗室研究。
- 對本論文：可支撐「MR＋生成式 AI 研究很少」，但目前只有這一份預印本，要再找第二份回顧交叉確認。
- 推論（待驗證）：文中描述的系統沒有一個在改變真實物體的外觀。
