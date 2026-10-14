# Workflow Notes

## Purpose and visual scope

This repository documents a personal Stable Diffusion WebUI NeoForge workflow for **Cute Anime Portrait / Soft Cel Shading / Clean Line Art / Minimal Graphic Background**. It focuses on portraits, character illustrations, and simple graphic backgrounds. The project does not claim new diffusion algorithms or emphasize large action poses or pose consistency.

## Signature Style Preset

The fixed artist-tag and style-LoRA combination is treated as one preset. No individual-tag attribution or ablation is included in V0.1. The exact reusable text is in [`../style/signature-style.txt`](../style/signature-style.txt).

## Verified baseline metadata

The source PNG `00036-1872344064.png` records the following settings. The PNG itself is not included in this repository.

| Setting | Recorded value |
| --- | --- |
| Interface | Stable Diffusion WebUI NeoForge, `neo-2.26` |
| Checkpoint | `reedXXXIllustrious_v160`, hash prefix `dd984164e4` |
| VAE module | `sdxl_vae` |
| Sampler | Kohaku LoNyu Yog |
| Scheduler | Karras |
| Steps / CFG | 30 / 3.5 |
| Seed / size | 1872344064 / 832 × 1152 |
| Style LoRA | `nyalia`, 0.6 |

The representative Showcase image is a separate output. Its metadata records `waiNSFWIllustrious_v150` (hash prefix `befc694a29`), 20 steps, CFG 3.5, Kohaku LoNyu Yog + Karras, `nyalia` 0.6, ADetailer, and a 2× Hires pass using `4xNMKDSuperscale` (20 Hires steps, CFG 3). Do not combine those Showcase-specific values with the recorded baseline.

## Practical observations and limits

- The author often applies ADetailer because the checkpoint's original face details may not meet the intended preference.
- Complex backgrounds have been less reliable in the author's use, so the workflow favors simple backgrounds and character-centered composition.
- High-resolution refinement may improve some details but is optional and does not define the style.
- The signature style block is the central style configuration.

These are personal workflow observations, not controlled or general claims about all checkpoints or prompts.

## Sampler and scheduler

The preferred sampler is **Kohaku LoNyu Yog**, available through [Koishi-Star/Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler). The author's preference for **Karras** is based on practical visual judgment. The current sampler grid varies in pose, composition, and details, so it cannot establish a universal sampler advantage. The [Normal / Uniform / Karras grid](../examples/scheduler-comparison.jpg) varies schedule type according to its embedded X/Y/Z metadata. It documents that preference visually; pose and detail changes limit fine-grained visual attribution and broader claims.

The recorded 30-step baseline is a personal setting. It is not presented as a mathematical optimum or as the upstream extension's recommendation.

## Reproduction checklist

1. Install a compatible NeoForge release and the sampler extension using upstream instructions.
2. Obtain the checkpoint, VAE, and style LoRA from authorized original sources; this repository does not redistribute weights.
3. Load the full Signature Style Preset from `style/signature-style.txt` as one positive-prompt block.
4. For the recorded baseline, configure the verified checkpoint, Kohaku LoNyu Yog, Karras, 30 steps, CFG 3.5, and `nyalia` at 0.6.
5. Apply ADetailer as needed for face refinement. Treat high-resolution refinement as optional.
6. Record extension version and any downstream refinement settings when generating future comparisons.

Exact output may differ across versions and environments. Extension version, full machine/runtime details, and separate baseline refinement settings remain TODO.
