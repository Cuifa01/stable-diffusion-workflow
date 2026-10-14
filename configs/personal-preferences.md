# Personal NeoForge Settings — Myon_style

This file records **current personal settings** for the **Myon_style** visual style in Stable Diffusion WebUI **NeoForge**. It is separate from the historical **Showcase1/comparison baseline** in [`baseline.yaml`](baseline.yaml). Parameters are based on the author's NeoForge screenshots and later direct confirmation; they are not independently extracted from the exported Showcase image.

## Current Base Generation

| Setting | Current preference | Source / status |
| --- | --- | --- |
| Base portrait resolution | **896 × 1152** | Latest direct confirmation (2026-10-14) |
| Checkpoint family | **WAI-illustrious-SDX / WAI-Illustrious (SDXL-based)** | The author uses versions **above 15.0** for this style; this is a usage preference, not a version-by-version test |
| VAE | **Checkpoint/default VAE configuration** | Already configured for the author's current setup; no manual separate VAE selection needed |
| Sampler | **Kohaku LoNyu Yog** | Provided by the [Euler-Smea-Dyn-Sampler extension](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler) |
| Scheduler | **Karras** | Personal preference |
| Sampling steps | **30 preferred** | The earlier Showcase/reference used 20 |
| CFG scale | **3.5 preferred** | Based on the author's visual comparisons |
| Batch count / batch size | **1 / 1** | Earlier NeoForge UI capture |

**Resolution correction:** An earlier NeoForge screenshot, supplied on 2026-10-14, showed **832 × 1152**. The author's subsequent explicit clarification established **896 × 1152 as the regular/current portrait starting resolution**. Both are historical facts about different records; the old value should not be used as the current default.

**Style and LoRA naming:** `Myon_style` names the visual style. The published workflow's fixed preset currently uses artist-style tags and the external [nyalia LoRA](https://civitai.com/models/834822/nyalia-illustrious) at weight `0.6`. A separate **Myon_style LoRA** is still being trained and is **not** part of this published generation configuration.

## Why I Prefer CFG 3.5

I compared **1.0 / 2.0 / 3.0 / 3.5 / 4.0 / 4.5 / 5.0 / 6.0** using the Showcase-style setup. Values below **3.5** appeared grayer and less detailed, while values from **3.5 upward** showed clearer lines; increasing CFG further emphasized the outlines. **3.5** is my preferred balance, although higher values were also usable in this style.

The [CFG comparison grid](../examples/comparisons/cfg-comparison.jpg) is available in the repository. These are qualitative personal observations, not a general optimum or a numerical quality claim.

## Optional High-Resolution Refinement (Hires.fix)

These settings were **visible in an earlier NeoForge UI screenshot**. They describe a configured **optional** pass and should not be assumed to have been active for every published image.

| Setting | Recorded UI value |
| --- | --- |
| Upscaler | **4xNMKDSuperscale** (visible name prefix; full selected name was truncated) |
| Hires steps | **12** |
| Denoising strength | **0.2** |
| Upscale by | **2×** |
| Resize width / height | **0 / 0** (no explicit target dimensions entered) |
| Hires CFG scale | **3** |

The relatively low denoising strength is intended to preserve the initial image's style and layout while permitting limited detail refinement. This is a personal choice, not a measured optimum.

## Distinguishing the Historical Reference

| Item | Historical Showcase1 / visual test reference | Current personal use |
| --- | --- | --- |
| Checkpoint | `waiNSFWIllustrious_v150` (previously documented reference) | WAI-illustrious-SDX / WAI-Illustrious family; author uses versions above 15.0 |
| Base portrait resolution | **Unknown** from the exported Showcase PNG | **896 × 1152** |
| Sampling steps | **20** | **30 preferred** |
| CFG | **3.5**, except when explicitly varied | **3.5 preferred** |
| Seed | `2601892452` | Selected per image |
| VAE | Historical VAE choice is not independently recoverable | Checkpoint/default VAE configuration |

The exported Showcase file is **1479 × 2048**, but its export dimensions must **not** be treated as its initial sampling resolution. Its supplied copy lacks readable generation metadata. The historical reference and the newer personal preferences are intentionally kept separate.

Detailed process: [`../docs/workflow.md`](../docs/workflow.md). Original positive/negative prompts: [`../docs/prompt-structure.md`](../docs/prompt-structure.md).
