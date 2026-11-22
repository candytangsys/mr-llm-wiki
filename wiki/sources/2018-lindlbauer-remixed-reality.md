---
type: source
title: "Remixed Reality: Manipulating Space and Time in Augmented Reality"
authors: [David Lindlbauer, Andrew D. Wilson]
year: 2018
venue: "CHI 2018"
evidence: peer-reviewed
raw: "raw/3173574.3173703.pdf"
url: ""
doi: "10.1145/3173574.3173703"
read_depth: partial
pipeline: [step-4-composite, step-2-locate, step-1-segment]
rq: [rq2-stability]
topics: []
as_of:
ingested: 2026-11-22
updated: 2026-11-22
review: approved
flags: [partial-read]
---

# Remixed Reality: Manipulating Space and Time in AR (Lindlbauer & Wilson, CHI 2018)

Read: abstract, introduction, related work (pp. 1–3), implementation performance (p. 7), limitations, discussion, conclusion (pp. 9–10). Skipped: detailed taxonomy walk-through and applications (pp. 4–6, 8).

## Summary
Instead of showing a camera image, Remixed Reality shows the user (in a VR headset) a live 3D reconstruction of their room from several external depth cameras. Because the room is now geometry, it can be edited as easily as a virtual scene: erase or move objects, change their appearance, pause or replay time, and move the viewpoint. Edits are stored in a voxel grid and applied to the live geometry every frame.

## Key claims
- Taxonomy of manipulations: spatial (e.g., erasing objects), appearance (e.g., changing textures), temporal (e.g., pausing time), and viewpoint. (p. 1) `peer-reviewed`
- Removing a real object in classic MR is hard: it needs precise alignment, the background behind the object, and a display able to cover the object; a front-facing camera cannot see behind it. (p. 1)
- Edits are recorded in a voxel grid and applied continuously to live geometry, so a moved or recoloured object keeps updating in real time. (pp. 1–2)
- Spatial AR systems such as Shader Lamps can change colour, texture or size, but "more dramatic changes such as completely removing an object are challenging". (p. 3)
- Setup: eight Kinect v2 cameras for a room of about 4 × 5 m; an HTC Vive headset. (pp. 4, 7)
- Rendering runs at up to 100 frames per second on the client, above the Kinects' typical 30 fps. (p. 7)
- Limitations: visual quality depends on depth camera resolution and placement; installing many cameras may not be feasible; haptics no longer match after edits. (pp. 9–10)
- The current version has no segmentation or object knowledge; adding scene understanding is future work. (p. 10)

## Numbers and conditions
| Metric | Value | Conditions | Page |
|---|---|---|---|
| Render rate | up to 100 fps | commodity gaming PC client; 8 Kinect v2; room about 4 × 5 m | 7 |
| Capture rate | about 30 fps | Kinect v2 | 7 |
| Network load | about 400 Mbit/s | 8 Kinects, compressed depth and colour | 7 |

## Relevance to this thesis
- [[appearance-editing-of-real-objects]], [[step-4-composite]]: appearance change (recolouring, textures) of real objects is one of four manipulation types; this is the closest prior system to restyling.
- [[step-1-segment]]: the paper names missing object segmentation as a limitation, which is exactly step 1 of this thesis's pipeline.
- [[rq2-stability]]: by reconstructing the room, edits stay attached to moving geometry; the cost is heavy infrastructure.

> [!inference] Our reading
> Remixed Reality reaches stable editing by replacing the camera image with 3D reconstruction from fixed cameras. MVP-1 cannot install eight Kinects; it has to get stability from a single moving phone camera, which is harder but deployable.

## Links and contradictions
- Related: [[2001-raskar-shader-lamps]], [[2017-mori-diminished-reality-survey]] (erasing objects is diminished reality), [[optical-vs-video-see-through]].
- No contradictions.

## 中文說明
- 使用者戴 VR 頭戴，看到的不是相機畫面，而是 8 台深度相機即時重建的房間 3D 模型，所以可以像編輯虛擬場景一樣編輯真實房間。
- 四類操作：空間（刪除、移動物件）、外觀（換顏色、換材質）、時間（暫停、重播）、視角（瞬移）。
- 渲染可達 100 fps；限制是畫質受相機解析度影響、要裝很多相機、沒有物件分割。
- 對本論文：這是最接近「改造真實物體外觀」的系統之一；它沒有分割，正好是本論文 pipeline 的第一步。
