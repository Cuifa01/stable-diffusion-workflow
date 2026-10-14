# Comparison plan — v1 (four pairs only)

**Goal:** Explain why the author prefers the documented workflow. These are visual demonstrations, not statistical evidence of general model superiority.

## Rules for fair comparisons

- Change **only one named variable** per comparison.
- Use the same checkpoint, full prompt/style block, LoRA, image dimensions, seed, CFG and steps unless the variable under test requires a change.
- For sampler/scheduler comparisons, turn **off** ADetailer and high-resolution refinement to prevent confounding.
- Record the full settings and image filenames for both outputs.
- Matched seeds reduce unnecessary variation, but different samplers/schedules can produce different trajectories/compositions; **same seed does not prove perfectly controlled image identity**.
- Write conclusions **after** looking at the actual pair. Prefer `in this example` over `always`.
- If time permits, repeat with a second seed; this is optional for v1.

## Required image 01 — Sampler

| Left | Right |
| --- | --- |
| Euler + Karras | Kohaku LoNyu Yog + Karras |
| [PLACEHOLDER: left image] | [PLACEHOLDER: right image] |

Output composite: `examples/01-sampler-comparison.png`  
Fixed: checkpoint, prompts, LoRA, seed, 30 steps, CFG 3.5, base resolution.  
Focus: line clarity, blur, unwanted texture, overall character appearance.  
Result: **TODO**.

## Required image 02 — Scheduler

| Left | Right |
| --- | --- |
| Kohaku LoNyu Yog + Normal | Kohaku LoNyu Yog + Karras |
| [PLACEHOLDER: left image] | [PLACEHOLDER: right image] |

Output composite: `examples/02-scheduler-comparison.png`  
Fixed: everything except schedule type.  
Focus: line quality, color transitions, artifacts.  
Result: **TODO**.

## Required image 03 — ADetailer

| Left | Right |
| --- | --- |
| Base image without ADetailer | Same base image refined with ADetailer |
| [PLACEHOLDER: full image / face crop] | [PLACEHOLDER: full image / face crop] |

Output composite: `examples/03-adetailer-comparison.png`  
Focus: face proportions, eyes, eyelashes, consistency with the original.  
Also show whether a changed expression or over-refined face is a possible trade-off.  
Result: **TODO**.

## Required image 04 — High resolution

| Left | Right |
| --- | --- |
| Original/base output | Same image after documented refinement |
| [PLACEHOLDER: full image / matched crop] | [PLACEHOLDER: full image / matched crop] |

Output composite: `examples/04-hires-comparison.png`  
Focus: small edges, hair strands, clothing folds; document method, size, upscale factor and denoise.  
Result: **TODO**.

## Optional (not required on day one)

- CFG scale: small 3-panel comparison (e.g. lower / 3.5 / higher), changing only CFG.
- Steps: small 3-panel comparison (e.g. lower / 30 / higher), changing only steps; record runtime.
- Background complexity: simple vs detailed (only if making a direct comparative claim later).
- Alternative face-refinement tools: only if the author has actually tested those tools.

## Image presentation specification

- Label every panel with the **changed setting** and its value.
- Show side-by-side images at the **same displayed dimensions**.
- For face/upscale, add **matched coordinate crops at comparable output sizes**.
- Prefer SFW example outputs and do not redistribute checkpoint or LoRA weights without permission.
