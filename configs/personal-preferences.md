# Personal NeoForge Settings

This file documents my **current working preferences** from NeoForge settings screenshots supplied on 2026-10-14. These values describe the UI configuration I commonly use; they are **not** proof that every Showcase or comparison image was rendered with them.

## Base generation

| Setting | Current preference |
| --- | --- |
| Width × height | **832 × 1152** |
| CFG scale | **3.5** |
| Batch count | **1** |
| Batch size | **1** |

The preferred sampler is **Kohaku LoNyu Yog + Karras**. I generally favor **30 sampling steps** for this style, although the published Showcase reference and sampler comparison are documented at **20 steps**.

## Optional high-resolution refinement (Hires.fix)

| Setting | Value shown in NeoForge |
| --- | --- |
| Upscaler | **4xNMKDSuperscale** (visible name prefix; full UI selection is truncated in the screenshot) |
| Hires steps | **12** |
| Denoising strength | **0.2** |
| Upscale by | **2×** |
| Resize width | **0** (no explicit target width entered) |
| Resize height | **0** (no explicit target height entered) |
| Hires CFG scale | **3** |

**Hires.fix is optional** in this style-first workflow. These are saved/displayed settings, not a claim that Hires.fix was enabled for every image, nor that these exact parameters produced the earlier Showcase file.

### Why I use these settings

- The relatively low **0.2 denoising strength** is intended to preserve the base composition and visual style during refinement while allowing limited additional detail. This is an intended trade-off, not an experimentally established optimum.
- A **2× upscale** is a convenient enhancement when more output resolution is needed.
- **12 Hires steps** and **Hires CFG 3** are personal UI settings, recorded for reproducibility rather than advertised as generally optimal.

## Distinguishing these preferences from the comparison baseline

The Showcase/test reference remains `waiNSFWIllustrious_v150`, `Kohaku LoNyu Yog + Karras`, **20 steps**, **CFG 3.5**, and seed **`2601892452`** based on the author's earlier confirmation. Its original generation resolution and the exact Hires parameters of that specific published image have **not** been verified through the re-uploaded export. The present **832 × 1152** base resolution is from the later NeoForge settings screenshot, not from readable metadata in that Showcase file.

For the reference-specific configuration, see [`baseline.yaml`](baseline.yaml); for prompt details, see [`../docs/prompt-structure.md`](../docs/prompt-structure.md).
