---
type: rq
id: rq2-stability
pipeline: [step-1-segment, step-2-locate, step-4-composite, step-5-stability]
sources: 4
updated: 2026-11-22
---

# RQ2 — How to keep the restyling stable under motion and lighting change?

Question: how can the restyled appearance stay attached and consistent while the camera moves and the lighting changes?
Related steps: [[step-1-segment]], [[step-2-locate]], [[step-4-composite]], [[step-5-stability]]

## Related work
| Approach | Source | Motion or lighting handled | Evidence |
|---|---|---|---|
| OST headsets: spatial calibration, latency, and light control as the three barriers to realism | [[2021-itoh-ost-hmd-survey]], pp. 27–28 | Both, for OST displays | peer-reviewed (partial read) |
| Geometric, photometric, temporal inconsistency as the DR framing | [[2017-mori-diminished-reality-survey]], pp. 1, 4 | Both | peer-reviewed |
| Projection needs a neutral surface and dark ambient light | [[2001-raskar-shader-lamps]], p. 9 | Lighting (as a limitation) | peer-reviewed |
| Edits follow live geometry from fixed depth cameras | [[2018-lindlbauer-remixed-reality]], pp. 1–2, 9 | Motion | peer-reviewed |

## Gap
Only `review: approved` sources here.

Tentative gap (4 sources). Approved systems get stability from controlled conditions: fixed depth cameras around the room ([[2018-lindlbauer-remixed-reality]], pp. 4, 7) or a dark room with a neutral surface ([[2001-raskar-shader-lamps]], p. 9). DR names the problems as geometric, photometric, and temporal inconsistency ([[2017-mori-diminished-reality-survey]], p. 1), and OST headsets add calibration and light-control barriers ([[2021-itoh-ost-hmd-survey]], pp. 27–28). None of the approved sources keeps a generated appearance stable with one moving phone camera under changing light.

## Candidate directions

> [!inference]
> (none yet)

## Sources
- [[2021-itoh-ost-hmd-survey]] (partial read)
- [[2017-mori-diminished-reality-survey]]
- [[2001-raskar-shader-lamps]]
- [[2018-lindlbauer-remixed-reality]]

## 中文說明
- 如何讓改造在移動與光線變化下保持穩定。
- 暫定缺口：現有系統靠「控制環境」換取穩定（裝 8 台深度相機、暗房加白色物體）。
- DR 把問題分成幾何、光度、時間三種不一致，可以當 RQ2 的分析框架。
- 沒有來源處理「單支移動手機、光線變化下，生成外觀如何保持穩定」。
