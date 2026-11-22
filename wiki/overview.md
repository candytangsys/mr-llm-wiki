---
type: overview
updated: 2026-11-22
---

# Overview — Personal-style MR: restyling real objects with generative AI

## Thesis in one paragraph (draft, from the vision draft of 2026-10-27, not evidence)
A mixed-reality system that recognizes real objects and walls, generates a new appearance from the user's own style description with generative AI, and keeps that appearance attached to the real object as it moves. The core contribution is restyling real objects; floating windows already exist on current headsets and are not the novelty.

## Status by pipeline step
| Step | Sources | Best known approach | Main gap |
|---|---|---|---|
| [[step-1-segment]] | 0 | — | — |
| [[step-2-locate]] | 1 | OST calibration only (not phone) | Not established; no phone sources |
| [[step-3-generate]] | 2 | Style-image-conditioned texture generation (CTGAN, virtual 3D only) | Not established; real-object generation not searched yet |
| [[step-4-composite]] | 1 | Compositing in camera-image space (VST) | Not established |
| [[step-5-stability]] | 2 | No method with numbers yet | Latency under-addressed (2 sources); flicker not covered |
| [[step-6-control]] | 2 | Natural language dominant; image input less common | Not established |

Background: [[2025-scrivener-intro-xr-book]] (edited volume, table of contents only). Concept: [[optical-vs-video-see-through]].

## Status by research question
| RQ | Sources | Gap (approved sources only) |
|---|---|---|
| [[rq1-waiting]] | 2 | Approved sources only discuss reducing latency, not what to show while waiting; HCI waiting literature still missing |
| [[rq2-stability]] | 1 | Not established (one partial, OST-only source) |
| [[rq3-style-control]] | 2 | Tentative: natural-language input dominates in GenAI-XR; image-based style control less used (single preprint) |

## Current position
Only `review: approved` sources may be cited here (AGENTS.md §9.3).

Tentative, from 4 approved sources: two preprints, one survey read in part, one textbook read at the contents level.
- Generative AI in mixed reality is rare in the reviewed GenAI-XR literature: 1 of 26 studies ([[2025-ning-genai-xr-review]], p. 10; `single-source`, preprint).
- Phone-based video see-through is the easier route to coherent compositing; optical see-through headsets cannot fully control light ([[2021-itoh-ost-hmd-survey]], pp. 2, 27–28). This supports building MVP-1 on a phone first.
- Latency is under-addressed both in GenAI-XR and in AR generally ([[2025-ning-genai-xr-review]], p. 15; [[2021-itoh-ost-hmd-survey]], p. 27).
- No approved source changes the appearance of a real object. The core gap is therefore not established yet: the wiki has not looked for that literature (Priority 1 in [[2026-11-22-coverage]]).

## Seed sources to collect
Reading list for the research side: [[2026-11-22-coverage]].

The vision draft mentions these items, but their original articles are not in raw/ yet, so the wiki cannot cite them. Clip each one into `raw/news/` or `raw/papers/` and ingest it; the vision draft notes the platform reports are old and their current status is unchecked.

| Item | Original outlet named in the draft | Maps to | Check |
|---|---|---|---|
| Decart MirageLSD real-time video generation | The Decoder, 2025-07 | [[step-3-generate]], [[step-5-stability]], [[rq1-waiting]] | Figures are company claims; look for a paper or benchmark |
| Meta Quest 3/3S Passthrough Camera API | Road to VR, 2025-03 | camera access | Is it still experimental? Can apps ship? |
| Android XR camera access | Road to VR, 2025-02 | camera access | Still a preview? |
| Apple Vision Pro camera access | no source named | camera access | Enterprise-only still? Find a source |
| XR headset and glasses shipments, 2026 Q2 | IDC | XR market | Get the IDC release itself |
| Snap Specs consumer version | Snap (event 2026-06-16); price and volume from ppc.land | platform | Separate official facts from rumors |
| Snap Lens Creator Rewards | Adweek, 2023 | creator income | Current status unknown |

## 中文說明
- 研究主軸：真實物品被使用者的風格改造，不是浮動視窗。
- 六個 pipeline 步驟與三個研究問題目前都還沒有來源。
- 「Current position」只能引用審查通過的來源；batch-1 通過後寫入了暫定論點：MR＋生成式 AI 很少、手機 VST 較容易、latency 研究不足。
- 核心缺口（改變真實物體外觀）還不能主張，因為還沒找過這類文獻。
- 上表是願景草稿裡提到但還沒存原文的資料，存進 raw/ 並 ingest 後才能引用。
