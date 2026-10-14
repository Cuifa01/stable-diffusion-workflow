# Myon_style LoRA Training — In Progress

**Status:** In progress (as reported by the author, October 2026)  
**Experiment:** Personal **Myon_style** style LoRA for the SDXL/Illustrious-oriented NeoForge image-generation workflow.

## Scope

The goal of this experiment is to train a personal style LoRA associated with the **Myon_style** aesthetic documented in this repository: anime illustration, soft cel shading, clean linework, expressive faces, and comparatively simple backgrounds.

**Important distinction:** `Myon_style` is already the author's name for the visual style. The **training-stage Myon_style LoRA** is a *separate, unfinished model*. Existing Showcase images and parameter-comparison grids were generated with the [external nyalia LoRA](https://civitai.com/models/834822/nyalia-illustrious) at weight `0.6` as part of the documented [Signature Style Preset](../style/signature-style.txt), **not with a completed Myon_style LoRA**.

## Training Record

| Item | Currently documented |
| --- | --- |
| Project name | `Myon_style` |
| Stage | **Training in progress** |
| Intended use | Style-consistent anime generation within the NeoForge / SDXL workflow |
| Dataset size, sources, licensing, and curation | **Not yet documented** |
| Training checkpoint and model compatibility | **Not yet confirmed for this LoRA experiment** |
| Training framework and hyperparameters | **Not yet documented** |
| Epochs, checkpoints, compute, and loss curves | **Not yet documented** |
| Generated evaluations and comparison grids | **Not yet published** |
| Release or download link | **None yet** |

## Next Documentation Milestones

- Record the training image sources, dataset selection, captions/tags, and usage permissions.
- Record the base checkpoint, training script/tool, LoRA configuration, optimizer, learning-rate schedule, and saved versions.
- Save reproducible evaluation prompts and settings, including checks of **style consistency** and **character/pose robustness**.
- Compare the trained style LoRA to the established `nyalia`-based workflow once actual results are available.
- Document limitations and unsuccessful experiments alongside successful ones.

These items are a **documentation plan**, not claims that the experiments, training runs, or evaluations have already been completed.

## Related Documents

- [NeoForge SDXL Workflow](../docs/workflow.md)
- [Prompt Structure](../docs/prompt-structure.md)
- [Visual Comparisons](../docs/comparisons.md)
- [Current Signature Style Preset](../style/signature-style.txt)

*This experiment does not claim a novel diffusion-model architecture or sampler algorithm.*
