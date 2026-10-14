# Workflow and configuration

## 1. Visual objective

**Cute Anime Portrait / Soft Cel Shading / Clean Line Art / Minimal Graphic Background.**

This project primarily documents a **single-character, stylized portrait workflow**. It does not require dynamic poses or complex scenes. Pose reference samples may be added later without being treated as a separate performance claim.

### Style block

The current artist-tag combination and style LoRA are handled as **one fixed style configuration**. We are **not** attributing individual visual effects to specific artist tags or conducting style-origin analysis. A future personal LoRA may replace or simplify this block.

**Exact prompt / tag block:** [TODO — insert after reviewing what to publish publicly.]

## 2. Known working baseline

One source PNG (`00036-1872344064.png`) has the following embedded parameters:

| Setting | Recorded value |
| --- | --- |
| Interface version | `neo-2.26` |
| Checkpoint | `reedXXXIllustrious_v160` |
| Model hash | `dd984164e4` |
| Sampler | `Kohaku LoNyu Yog` |
| Schedule type | `Karras` |
| Steps | `30` |
| CFG scale | `3.5` |
| Seed | `1872344064` |
| Base image size | `832 × 1152` |
| VAE / module | `sdxl_vae` |
| Style LoRA | `nyalia`, strength `0.6` |
| RNG | `GPU` |

This source PNG does not carry ADetailer or high-resolution-processing parameters. These settings must be documented separately from real test runs rather than inferred from the final image.

## 3. Sampler dependency

**External extension:** [Koishi-Star/Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler)

**Preferred sampler:** Kohaku LoNyu Yog  
**Preferred scheduler:** Karras

Personal rationale to test: cleaner-looking line work, less blur, and less visual clutter for this style.

**Important:** This is an *empirical preference*, not proof of a universally best sampler. The upstream author's 2024-08-31 note recommends **10 steps** for Kohaku LoNyu Yog and states it is a slower second-order method. The recorded **30 steps** should therefore be presented as a personal setting, not the developer's recommendation.

**TODO for reproducibility:** record extension commit/version, precise installation steps, GPU, CUDA/PyTorch versions if known, and actual generation time.

## 4. Why Karras?

The working configuration uses Karras. The `Normal` vs `Karras` comparison remains pending. Until it is generated, describe Karras as a personal preference only.

## 5. CFG scale and sampling steps

**CFG = 3.5** controls the degree of conditioning guidance used in sampling.  
**Steps = 30** controls the number of sampling iterations.

Both are **recorded configuration values**. They should be included in the reproducibility table. Their effects can depend on checkpoint, sampler, scheduler, and prompt, so **no separate CFG/Steps ablation is required for v1**. Do not claim 3.5 or 30 is mathematically optimal.

## 6. Face refinement (ADetailer)

**Practical motivation:** The author prefers additional face refinement because default facial details are often insufficient for the intended style.

**Comparison required:** same base result, with / without ADetailer; include one matching facial crop. This establishes the benefit over *no face refinement*, not superiority over untested alternatives.

**TODO — record exact:** detector model, confidence, mask blur/dilate, denoising strength, inpainting size/padding, positive/negative inpainting prompt, extension version.

## 7. High-resolution refinement

**Practical motivation:** The author finds additional high-resolution processing useful for preserving small visual details.

**Comparison required:** same source image before/after refinement; aligned crops of hair, eye or clothing regions.

**TODO — verify method:** Hires.fix vs external upscale vs img2img; upscaler, scale factor, denoising strength, steps, and output dimensions. A larger file alone does not identify which process was used.

## 8. Scene scope

The author generally favors minimalist/graphic backgrounds rather than detailed scenes, which have caused visually inconsistent results in prior personal use. Treat this as a **workflow scope and reported observation**, not a general model-wide finding.

## 9. Reproduction checklist

1. Install a compatible NeoForge version.
2. Install the referenced sampler extension and note its commit/version.
3. Obtain the checkpoint, VAE and LoRA from their original authorized sources.
4. Load the full positive/negative prompt and fixed style configuration.
5. Set checkpoint, sampler, scheduler, steps, CFG, seed and image size.
6. Recreate the base image, then apply the documented optional face/high-resolution steps.
7. Compare the result visually; exact cross-device/pipeline pixel equivalence is not guaranteed.

**Current status:** Full prompt and downstream refinement settings are awaiting the author's review before public release.
