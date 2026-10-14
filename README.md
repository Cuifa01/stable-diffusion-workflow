# Stylized Anime Portrait Generation Workflow

A personal **Stable Diffusion WebUI NeoForge** workflow focused on a distinctive anime-portrait style. **V0.1** documents the signature style preset, selected generation settings, visual comparisons, and practical limitations.

## 1. Project Overview

This repository documents how I build character-focused anime illustrations with a consistent visual identity. The project is a record of practical workflow design and personal visual evaluation; it does **not** claim a new diffusion model, sampler, or generation algorithm.

## 2. Style Overview

**Cute Anime Portrait / Soft Cel Shading / Clean Line Art / Minimal Graphic Background**

My workflow favors expressive characters, readable outlines, restrained shading, and simple graphic backgrounds. Rather than increasing detail everywhere, I focus on the face, silhouette, and overall balance of the illustration.

## 3. Signature Style Preset

The visual identity comes primarily from a fixed combination of artist-style tags and a style LoRA. I treat the complete combination as **one Signature Style Preset**, without attempting to isolate the influence of individual tags at this stage.

```text
artist:tianliang duohe fangdongye,
(kanpa \(campagne 9\):0.8),
(alpha \(alpha91\):0.6),
(koyama shigeru:0.6),
(massakasama:0.55),
<lora:nyalia:0.6>
```

Reusable preset: [`style/signature-style.txt`](style/signature-style.txt).

Style LoRA: [nyalia (Illustrious)](https://civitai.com/models/834822/nyalia-illustrious), weight `0.6`.

## 4. Style Showcase

<p align="center">
  <img src="examples/representative-result.png" alt="Representative anime portrait in the signature style" width="520">
</p>

This illustration serves as the **visual reference** for the comparisons below. As confirmed by the author and noted in earlier project records, the associated working setup uses **`waiNSFWIllustrious_v150`**, **Kohaku LoNyu Yog + Karras**, **20 steps**, **CFG 3.5**, **seed `2601892452`**, and **`nyalia` at 0.6**. The exported Showcase PNG supplied for this revision does not contain readable generation metadata, so these settings are recorded from the author's confirmation and the existing project notes rather than independently extracted from this export.

## 5. Sampler Comparison

<p align="center">
  <img src="examples/sampler-comparison.jpg" alt="Visual comparison of Euler, Euler a, and Kohaku LoNyu Yog" width="100%">
</p>

**Euler** produces unusual color patches around the hair edges, and the layering between elements is less clear. **Euler a** has messier highlights and shadows in the hair. Both also show some character-structure issues. In this comparison, **Kohaku LoNyu Yog** gives the cleanest overall result, with more coherent structure and lighting, making it my preferred sampler for this style.

Sampler source: [Koishi-Star/Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler).

## 6. Sampling Steps Comparison

<p align="center">
  <img src="examples/steps-comparison.jpg" alt="Comparison of 5, 10, 15, 20, 30, and 40 sampling steps" width="100%">
</p>

This grid varies the number of steps (**5, 10, 15, 20, 30, and 40**) while retaining the Showcase reference configuration for the other recorded settings. The lower-step samples look somewhat less resolved in places, while the higher-step outputs develop different small details and facial features. The change is not simply a linear increase in quality: composition and local features can shift as the step count changes.

Although the Showcase reference was generated with **20 steps**, I currently prefer **30 steps** when working with this style. That is a personal quality-versus-effort choice, not a universal or mathematically optimal setting.

## 7. Workflow Configuration

The Showcase and comparison grids use the **same author-confirmed reference setup**, except for the parameter deliberately varied in each comparison.

| Parameter | Reference setup | Notes |
| --- | --- | --- |
| Interface | Stable Diffusion WebUI NeoForge | Exact installed version should be recorded for future reproduction |
| Checkpoint | `waiNSFWIllustrious_v150` | Previously documented for the Showcase; differs from the older `reedXXXIllustrious_v160` example |
| Sampler | Kohaku LoNyu Yog | Varied only in the sampler comparison |
| Scheduler | Karras | Fixed preference; no scheduler comparison included |
| Steps | 20 | Showcase and sampler-grid reference; deliberately varied in the step grid |
| CFG scale | 3.5 | Fixed reference value |
| Seed | `2601892452` | Same seed across the test images, as confirmed by the author |
| Signature Style LoRA | `nyalia`, weight 0.6 | Part of the fixed style preset |
| VAE / initial resolution | To be confirmed | Do not infer these from the exported image size |

**Reproduction note:** This table describes the author's confirmed common test setup, not independently verified metadata for every exported image. The re-uploaded Showcase PNG has no readable parameter block. See [`configs/baseline.yaml`](configs/baseline.yaml) and [`docs/workflow.md`](docs/workflow.md).

## 8. Practical Experience & Limitations

- **Face refinement:** The base model's default facial details do not always meet my expectations. I use **ADetailer** when targeted refinement improves the expression and eye details without losing the intended style.
- **Backgrounds:** Detailed scenes have been less reliable in my own use. I therefore prefer simple color fields and limited decorative elements that keep the character as the focal point.
- **High-resolution processing:** Upscaling or a high-resolution pass can help with selected details, but it is **optional**. Higher pixel count alone is not the goal of this style.
- **Style priority:** The Signature Style Preset defines the desired look; sampling and refinement are practical choices made in service of that visual result.

## 9. Additional and Planned Comparisons

An initial [ADetailer example](examples/adetailer-comparison.jpg) is available, but a fully documented matched comparison is still planned. Future additions may include:

- ADetailer **OFF vs ON**, with complete face-refinement settings
- Optional high-resolution refinement **before vs after**
- Additional examples using the same Signature Style Preset

See [`docs/comparisons.md`](docs/comparisons.md). No results are claimed for comparisons that have not been completed.

## 10. Reproduction Guide

1. Install a compatible version of Stable Diffusion WebUI NeoForge.
2. Obtain `waiNSFWIllustrious_v150`, a compatible VAE, and the `nyalia` LoRA from their original sources. No model weights are redistributed here.
3. Install the [Euler-Smea-Dyn-Sampler extension](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler) and select **Kohaku LoNyu Yog**.
4. Apply the full Signature Style Preset from [`style/signature-style.txt`](style/signature-style.txt).
5. Start from **Karras**, **20 steps**, **CFG 3.5**, and **seed `2601892452`** to follow the documented Showcase reference. **30 steps** is an alternative personal preference illustrated by the step comparison.
6. Apply ADetailer only when desired, and record any high-resolution refinement separately. Exact face-refinement, upscale, base-size, and extension-version details still need to be documented.

Different extensions, software versions, or hardware configurations may produce different results even when these recorded settings match.
