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
| [[step-2-locate]] | 1 | OST calibration only (not phone) | pending review |
| [[step-3-generate]] | 2 | Style-image-conditioned texture generation (CTGAN, virtual 3D only) | pending review |
| [[step-4-composite]] | 1 | Compositing in camera-image space (VST) | pending review |
| [[step-5-stability]] | 2 | No method with numbers yet | pending review |
| [[step-6-control]] | 2 | Natural language dominant; image input less common | pending review |

Background: [[2025-scrivener-intro-xr-book]] (edited volume, table of contents only). Concept: [[optical-vs-video-see-through]].

## Status by research question
| RQ | Sources | Gap (approved sources only) |
|---|---|---|
| [[rq1-waiting]] | 2 | pending review |
| [[rq2-stability]] | 1 | pending review |
| [[rq3-style-control]] | 2 | pending review |

## Current position
Only `review: approved` sources may be cited here (AGENTS.md §9.3).

(none yet)

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
- 「Current position」只能引用審查通過的來源。
- 上表是願景草稿裡提到但還沒存原文的資料，存進 raw/ 並 ingest 後才能引用。
