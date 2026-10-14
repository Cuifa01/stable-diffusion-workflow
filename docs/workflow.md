# NeoForge SDXL Workflow — Myon_style

This document describes how I use **Stable Diffusion WebUI NeoForge** to produce the **Myon_style** visual aesthetic. It separates the **current daily-use configuration** from the **historical Showcase/reference experiment**, because the values have evolved over time.

**Myon_style** refers to my target visual style, not to an independently trained model. The existing examples use a fixed mix of artist-style tags plus the external **nyalia** LoRA. My personal **Myon_style LoRA** remains in training and is not used in the documented examples.

## 1. Model and Environment Setup

| Component | Current working choice | Notes |
| --- | --- | --- |
| Interface | Stable Diffusion WebUI **NeoForge** | Installed build/version still needs to be recorded |
| Model family | **WAI-illustrious-SDX / WAI-Illustrious, SDXL-based** | I can use versions **above 15.0** for this personal style; this is an author-reported compatibility preference, not a version-by-version benchmark |
| Checkpoint for published Showcase reference | `waiNSFWIllustrious_v150` | Historical documented setting; keep separate from the general supported checkpoint family |
| VAE | **Checkpoint/default VAE configuration** | Already configured in my setup; no separate VAE selection required for my current workflow |
| Sampler | **Kohaku LoNyu Yog** | Provided by [Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler) |
| Scheduler | **Karras** | Fixed personal preference; no scheduler comparison currently presented |

The exact checkpoint file/hash and NeoForge/extension revisions remain useful reproducibility details to record for a future environment snapshot. Do not assume the different compatible WAI-Illustrious versions produce identical images.

## 2. Prompt Construction

A standard positive prompt starts with quality tags, then separates the following functional blocks using `BREAK`:

1. Camera and composition
2. Pose and action
3. Character and expression
4. Body and outfit
5. **Fixed style preset**
6. Background

This lets me modify pose, character, outfit, and background while keeping the chosen visual style block consistent.

### Current Signature Style Preset

The fixed style block is the combination of artist-style tags and **[nyalia (Illustrious)](https://civitai.com/models/834822/nyalia-illustrious)** at weight `0.6`. It is stored as [`../style/signature-style.txt`](../style/signature-style.txt), with complete positive and negative prompt examples in [`prompt-structure.md`](prompt-structure.md).

**Important:** This existing `nyalia` LoRA is not my personal `Myon_style` LoRA, which is still under training. The current preset should not be rewritten as though the new model were finished.

## 3. Sampling and Base Generation

| Parameter | Current personal workflow | Previously published Showcase/reference |
| --- | --- | --- |
| Base portrait resolution | **896 × 1152** | Original size not independently recoverable from the exported file |
| Sampling steps | **30 preferred** | **20** |
| CFG scale | **3.5 preferred** | **3.5** (except CFG comparison) |
| Sampler / Scheduler | Kohaku LoNyu Yog / Karras | Kohaku LoNyu Yog / Karras (except sampler comparison) |
| Checkpoint | WAI-illustrious-SDX family; versions above 15.0 used in my workflow | `waiNSFWIllustrious_v150` |
| Seed | Chosen per generation | `2601892452` |
| Batch count / size | **1 / 1** as recorded in my NeoForge UI | Not independently recoverable from the Showcase export |

**Resolution update:** My latest confirmed regular portrait setting is **896 × 1152**. A previous NeoForge UI capture listed **832 × 1152**. The latest value is the current preference, but neither screenshot nor the exported **1479 × 2048** Showcase file establishes the actual initial resolution of that older Showcase generation. Its exported PNG does not include readable parameter metadata.

The base image is generated in NeoForge using the chosen checkpoint, prompts, fixed style preset, and sampler settings. **Hires.fix and ADetailer are optional**, not prerequisites for achieving the style.

## 4. Optional Refinement

### ADetailer

I use ADetailer when the initial output needs better face or eye details. The repository **already includes** an [ADetailer comparison image](../examples/adetailer-comparison.jpg) with labels for detector `None` and `99coins_anime_girl_face_m_seg.pt`; it should not be described as an experiment that has never been attempted.

For a fully reproducible matched **OFF vs ON** test, additional values—masking, denoising, inpainting settings, and the exact treatment conditions—would still need to be documented. The present example is an **initial visual comparison** rather than a fully specified experiment.

### Hires.fix

My optional Hires.fix settings, taken from a previous NeoForge UI configuration, are:

| Setting | Value |
| --- | --- |
| Upscaler | `4xNMKDSuperscale` (visible name prefix; complete selected name not verified) |
| Upscale by | **2×** |
| Hires steps | **12** |
| Denoising strength | **0.2** |
| Hires CFG scale | **3** |
| Resize width / height | **0 / 0** (no explicit final target dimensions entered) |

I use a relatively low denoising value with the intention of preserving style and composition while refining detail. This is a personal preference, not a measured optimum, and these settings are **not verified for every older exported image**.

## 5. Visual Evaluation and Parameter Comparisons

After generation, I visually inspect facial expressions, local anatomy, linework, shading, and overall **Myon_style** consistency.

| Comparison | What I observed |
| --- | --- |
| **Sampler**: Euler / Euler a / Kohaku LoNyu Yog | In the published examples, Kohaku gives my preferred structure and cleaner overall shading; Euler variants show some artifacts |
| **Steps**: 5 / 10 / 15 / 20 / 30 / 40 | Lower step values can be less resolved; I generally prefer 30 for everyday use, whereas the Showcase used 20 |
| **CFG**: 1.0 through 6.0 | Values below 3.5 can look grayer and less detailed; higher values emphasize outlines. My preference is 3.5 |
| **ADetailer** | An initial comparison image exists; full matched test parameters remain to be recorded |

See [`comparisons.md`](comparisons.md) for the existing grids and descriptive observations. The **CFG image has not yet been uploaded** to the repository, so the comparison remains text-only here.

These are personal visual studies, **not statistical benchmarks**. Where possible, I keep other settings fixed when varying one parameter. Matched seeds alone do not guarantee matching composition across different samplers.

## 6. Reproduction Checklist

1. Open a compatible **Stable Diffusion WebUI NeoForge** setup.
2. Load a suitable **WAI-illustrious-SDX / WAI-Illustrious** checkpoint with its already configured/default VAE.
3. Install the [Euler-Smea-Dyn-Sampler extension](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler) if needed for **Kohaku LoNyu Yog**.
4. Follow the six-part prompt layout in [`prompt-structure.md`](prompt-structure.md) and apply [`signature-style.txt`](../style/signature-style.txt).
5. For my **current** portrait workflow, start with **896 × 1152**, **Karras**, **30 steps**, and **CFG 3.5**; the showcased historical baseline uses **20 steps** and seed `2601892452`.
6. Optionally apply **ADetailer** or **Hires.fix**, recording their settings if you are preparing an experiment.
7. Evaluate the result visually and document any changed parameter.

Exact reproduction of the historical Showcase still depends on further environment and export details. The repository distinguishes those unknowns from the author's current settings rather than filling them in by assumption.

## 7. Ongoing Development

The broader project began in **July 2025** and was uploaded to GitHub more recently. Training of a separate **Myon_style LoRA** is **in progress** and is treated as an **Experiments** workstream, distinct from the already documented NeoForge generation workflow. No training outcome, accuracy, or released LoRA weights are claimed.
