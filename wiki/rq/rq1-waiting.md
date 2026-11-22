---
type: rq
id: rq1-waiting
pipeline: [step-3-generate, step-5-stability]
sources: 2
updated: 2026-11-22
---

# RQ1 — What should the space show while generation is slow?

Question: when generation takes longer than the user can wait, what should the space show in the meantime?
Background (not evidence): continues the Scaffold XR work.
Related steps: [[step-3-generate]], [[step-5-stability]]

## Related work
| Approach | Source | What it shows while waiting | Evidence |
|---|---|---|---|
| Latency and stuttering named as an open problem for generative AI in XR | [[2025-ning-genai-xr-review]], p. 15 | Not addressed | preprint |
| Latency rarely addressed in AR research | [[2021-itoh-ost-hmd-survey]], p. 27 | Not addressed | peer-reviewed |

## Gap
Only `review: approved` sources here.

In the approved sources, latency is something to reduce (edge deployment, compression, quantisation; [[2025-ning-genai-xr-review]], p. 15) or is noted as rarely studied ([[2021-itoh-ost-hmd-survey]], p. 27). Neither addresses what the user sees while generation is under way. Two sources; this is not yet evidence that the wider literature lacks it, because HCI work on waiting and progress feedback is not in the wiki.

## Candidate directions

> [!inference]
> Both sources treat latency as something to reduce, not as a state to design for. Literature on progress indicators and waiting in HCI is not in the wiki yet (see [[2026-11-22-coverage]]).

## Sources
- [[2025-ning-genai-xr-review]]
- [[2021-itoh-ost-hmd-survey]] (partial read)

## 中文說明
- 生成速度慢時，等待期間空間該呈現什麼。
- 兩個來源都承認 latency 是問題，但都只談「怎麼變快」，沒有談「等的時候給使用者看什麼」。
- 推論：這可能是本題的切入點，但要先補 HCI 等待與進度提示的文獻才能下結論。
