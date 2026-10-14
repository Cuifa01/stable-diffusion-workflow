# Workflow Notes

## Visual goal

**Cute Anime Portrait / Soft Cel Shading / Clean Line Art / Minimal Graphic Background.** This is a personal style-focused Stable Diffusion WebUI NeoForge workflow rather than a research claim about new diffusion methods. It prioritizes characters, clean line work, soft cel shading, and simple graphic backgrounds.

## Signature Style Preset

The artist-tag mix and `nyalia` style LoRA form one fixed Signature Style Preset. The workflow currently treats these as a whole and does not attempt to attribute visual characteristics to individual artists. Exact text: [`style/signature-style.txt`](../style/signature-style.txt).

## Reference configuration for the published comparisons

The author confirms that the comparisons are based on the same Showcase1 style, checkpoint, seed, and other settings **except the compared parameter**.

| Setting | Current Showcase / test reference |
| --- | --- |
| Checkpoint | `waiNSFWIllustrious_v150` |
| Sampler | Kohaku LoNyu Yog (except sampler grid) |
| Scheduler | Karras |
| Steps | 20 (except step grid) |
| CFG | 3.5 |
| Seed | `2601892452` |
| Style LoRA | `nyalia`, 0.6 |
| VAE, initial resolution | To be confirmed |

The re-uploaded Showcase PNG is **1479 × 2048** and contains no readable generation parameter block. Therefore the table reflects the author's confirmation and the previously documented Showcase settings, rather than a fresh metadata extraction. The earlier `reedXXXIllustrious_v160` / 30-step / seed `1872344064` example is a **different generation** and is **not the reference for these published comparisons**.

## Sampler and Karras

The preferred sampler is **Kohaku LoNyu Yog**, from [Koishi-Star/Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler). In the present sampler grid, Euler shows unexpected color patches near the hair edges; Euler a produces busier and less orderly hair lighting; Kohaku appears more cohesive without comparable distracting artifacts. These observations support a **personal preference for this image style**, not a universal claim.

**Karras** remains the fixed scheduler setting used with the preferred sampler. No scheduler comparison is presented in this version.

## Steps and CFG

**20 steps** is the reference used for the Showcase image and sampler comparison, whereas **30 steps** is the author's current practical preference shown in the step grid. A higher step count can change local details or even the image composition, not just add sharpness. CFG is fixed at **3.5** in the documented comparisons. Neither value should be described as mathematically optimal.

## Refinement and limitations

- **ADetailer:** Often useful when the base model's facial details fall short of the intended style. Record detector, denoise, mask and inpainting settings when adding complete before/after demonstrations.
- **High-resolution refinement:** Optional and not the primary source of the chosen style. Confirm the exact method, steps, scale and upscaler when documenting a specific result.
- **Background complexity:** The author generally prefers minimal graphic backgrounds because detailed scenes have been less reliable in personal tests.
- **Style priority:** Maintain the fixed style block when varying sampler or step count.

## Reproduction checklist

1. Install a compatible NeoForge version and the [sampler extension](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler); record actual versions for reproducibility.
2. Obtain the stated checkpoint, a compatible VAE, and `nyalia` LoRA from original authorized sources.
3. Apply the Signature Style Preset and the rest of the matching prompt.
4. Start from Kohaku LoNyu Yog + Karras, 20 steps, CFG 3.5 and seed `2601892452`; use 30 steps if exploring the author's separately stated preference.
5. Use ADetailer where desired and keep optional high-resolution passes distinct from the core style configuration.

Exact replication also requires the complete prompts, VAE, original resolution, extension version, and downstream processing settings, some of which are not yet documented.
