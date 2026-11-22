---
type: concept
aliases: [DR, illusionary transparency]
pipeline: [step-1-segment, step-2-locate, step-4-composite, step-5-stability]
rq: [rq2-stability]
sources: 2
updated: 2026-11-22
flags: []
---

# Diminished reality

## Definition
Methods that visually conceal, eliminate, or see through real objects in real time, the opposite of AR's adding of virtual objects ([[2017-mori-diminished-reality-survey]], p. 1). Removing objects in classic MR is hard because the camera cannot see what is behind them ([[2018-lindlbauer-remixed-reality]], p. 1).

## Approaches in the literature
| Function | Sources | What it does |
|---|---|---|
| Diminish | [[2017-mori-diminished-reality-survey]], p. 2 | Degrade part of the view |
| See-through | same, p. 2 | Show the hidden background |
| Replace | same, p. 2 | Cover a real object with a virtual one |
| Inpaint | same, p. 2 | Generate a plausible background |
| Erase via multi-camera reconstruction | [[2018-lindlbauer-remixed-reality]], pp. 1–3 | External cameras see behind the object |

Typical procedure: background observation, scene tracking, region-of-interest detection, hidden view generation, composition ([[2017-mori-diminished-reality-survey]], pp. 3–4).

## Relevance to this thesis
Restyling is DR's "replace" with generated content. DR's procedure and its geometric, photometric, temporal inconsistency classes give this thesis a vocabulary for [[step-4-composite]] and [[rq2-stability]].

## Open problems
- Ground truth for evaluation is hard to obtain; OST DR is barely explored. ([[2017-mori-diminished-reality-survey]], p. 10)

## 中文說明
- 讓真實物體看起來消失、被遮住或變透明，方向跟 AR 相反。
- 四種功能：弱化、看穿、替換、補背景；本論文的「改造外觀」對應「替換」。
- 不一致分為幾何、光度、時間三類，是 RQ2 可以借用的框架。
