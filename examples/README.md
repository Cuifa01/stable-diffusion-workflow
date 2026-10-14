# Image Examples

Images are arranged by their role in the **Myon_style / NeoForge SDXL** workflow. Original image files were moved without re-encoding or altering their binary content.

## Showcase

| File | Content |
| --- | --- |
| [`showcase/representative-result.png`](showcase/representative-result.png) | Representative Myon_style visual target and Showcase1 reference |

## Active Visual Comparisons

| File | Content |
| --- | --- |
| [`comparisons/sampler-comparison.jpg`](comparisons/sampler-comparison.jpg) | Euler / Euler a / Kohaku LoNyu Yog |
| [`comparisons/steps-comparison.jpg`](comparisons/steps-comparison.jpg) | 5 / 10 / 15 / 20 / 30 / 40 sampling steps |
| [`comparisons/adetailer-comparison.jpg`](comparisons/adetailer-comparison.jpg) | Existing initial ADetailer comparison; full matched OFF/ON parameters are not yet documented |
| [`comparisons/cfg-comparison.jpg`](comparisons/cfg-comparison.jpg) | CFG 1.0 / 2.0 / 3.0 / 3.5 / 4.0 / 4.5 / 5.0 / 6.0 — compressed JPEG, **uploaded** |

## Historical Archive

| File | Reason retained |
| --- | --- |
| [`comparisons/archive/scheduler-comparison.jpg`](comparisons/archive/scheduler-comparison.jpg) | Earlier scheduler grid, retained for history but **excluded from the current comparisons** |

## Reference Notes

The published Sampler and Steps grids are documented against the **historical Showcase1 setup**, including `waiNSFWIllustrious_v150`, CFG `3.5`, and seed `2601892452`, except for the explicitly varied parameter. The historical Showcase used **20 steps**; **30 steps** is the author's later everyday preference.

The user's current regular portrait resolution is **896 × 1152**, whereas the older exported Showcase image does not contain readable generation metadata that independently confirms its initial resolution.

See [`../docs/comparisons.md`](../docs/comparisons.md) and [`../configs/baseline.yaml`](../configs/baseline.yaml). The new personal **Myon_style LoRA** is [still in training](../experiments/lora-training.md); it was not used to produce these published grids.

No model or LoRA weights are distributed in this repository.
