---
type: pipeline
id: step-5-stability
rq: [rq1-waiting, rq2-stability]
sources: 2
updated: 2026-11-22
---

# Step 5 — Stability and latency

Scope (AGENTS.md §2): frame-to-frame consistency, no flicker, low latency. The hardest step.
Current prototype (background, not evidence): Repaint latency 130–135 ms; continuous mode is unstable.
MVP-1 acceptance (proposed in the vision draft): click-to-display latency no higher than Repaint's 130 ms; the pattern stays on the object for 10 s of slow camera motion; usable in at least 3 lighting conditions.

## Methods in the literature
| Method | Source | Speed and conditions | Fits MVP-1? |
|---|---|---|---|
| Edge deployment, model compression, quantisation for generative models in XR | [[2025-ning-genai-xr-review]], p. 15 | No numbers given | Unclear |
| Foveated rendering to cut rendering load and latency (OST) | [[2021-itoh-ost-hmd-survey]], p. 27 | Not read in detail | No: headset-specific |

## What is solved
Nothing with numbers yet. Both sources describe latency as under-addressed: in GenAI-XR ([[2025-ning-genai-xr-review]], p. 15) and in AR generally ([[2021-itoh-ost-hmd-survey]], p. 27).

## Gap
Only `review: approved` sources here. (none approved yet)

## Sources
- [[2025-ning-genai-xr-review]]
- [[2021-itoh-ost-hmd-survey]] (partial read)

## 中文說明
- 穩定與低延遲：逐幀一致、不閃爍，是最難的一步。
- 兩個來源都說 latency 很少被處理，但都沒有給數據。
- 時間一致性（temporal consistency）、閃爍處理的方法來源還完全沒有。
