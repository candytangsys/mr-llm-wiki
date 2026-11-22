---
type: concept
aliases: [OST vs VST, see-through displays, video see-through, optical see-through]
pipeline: [step-4-composite, step-2-locate]
rq: [rq2-stability]
sources: 1
updated: 2026-11-22
flags: [single-source]
---

# Optical vs video see-through

## Definition
Video see-through (VST) shows the real world through a camera feed, as in phone-based AR and VST headsets. Optical see-through (OST) overlays graphics on a semi-transparent display, so the user sees the real world directly. Spatial AR, or projection mapping, is a third route that projects onto real surfaces. ([[2021-itoh-ost-hmd-survey]], p. 2)

## Approaches in the literature
| Approach | Sources | Strength | Limits |
|---|---|---|---|
| VST (phone, VST headset) | [[2021-itoh-ost-hmd-survey]], p. 2 | Coherence is easier because merging happens in camera-image space | The user never sees the world directly; mutual eye contact is lost |
| OST headset | [[2021-itoh-ost-hmd-survey]], pp. 3, 27–28 | Real world at full fidelity; close to normal glasses | Coherence is harder; no full control over light; latency and colour rarely addressed |
| Spatial AR, projection mapping | [[2021-itoh-ost-hmd-survey]], p. 2 | Augments real surfaces directly | Needs geometric and radiometric alignment of projectors |

## Relevance to this thesis
MVP-1 runs in a phone browser, which is VST: the case where restyling by image compositing (mask, warp, Multiply) is possible ([[step-4-composite]]). The later headset version depends on which kind of headset.

> [!inference]
> Passthrough headsets such as Quest are VST, so the phone pipeline should carry over; OST glasses would limit darkening or replacing a real surface's appearance. Needs a source on passthrough headsets and a reading of Itoh §6.1 and §6.3.

Pending review (batch-2): most diminished reality systems are VST, and DR on OST displays is "virtually an unexplored area" ([[2017-mori-diminished-reality-survey]], pp. 3, 10). Remixed Reality is a fourth route: show a live 3D reconstruction instead of a camera image ([[2018-lindlbauer-remixed-reality]], p. 1).

## Open problems
- Per-pixel control of both added and filtered light in OST displays. ([[2021-itoh-ost-hmd-survey]], pp. 27–28)

## 中文說明
- VST（手機、passthrough 頭戴）透過相機畫面看世界，合成在影像空間完成，比較容易做到一致。
- OST（光學透視眼鏡）直接看到真實世界，但無法完全控制光線，要讓真實表面變暗或被取代很難。
- 投影式 AR 直接把影像投在真實表面上，需要幾何和輻射度校準。
- 本論文的 MVP-1 是 VST；未來上頭戴裝置時，要看是哪一種。
