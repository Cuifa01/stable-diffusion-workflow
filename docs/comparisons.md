# Myon_style — NeoForge SDXL Visual Comparisons

These examples document **personal visual observations** within the **Myon_style** aesthetic, using Stable Diffusion WebUI **NeoForge** and an Illustrious SDXL-family checkpoint. They are **not statistical benchmarks** or claims of general sampler superiority.

**Style/LoRA distinction:** `Myon_style` names the author's aesthetic, not a finished custom model. The existing examples use a fixed artist-style preset and the external **nyalia** LoRA at weight `0.6`. The separately planned **Myon_style LoRA** is still in training and does not appear in these results.

## Reference Setup and Experimental Scope

The following are the **author-confirmed historical Showcase1 reference settings**, not metadata extracted from the uploaded PNG.

| Parameter | Historical reference | Deliberately varied in |
| --- | --- | --- |
| Checkpoint | `waiNSFWIllustrious_v150` | Not varied in the documented grids |
| Sampler | Kohaku LoNyu Yog | Sampler comparison |
| Scheduler | Karras | Fixed; no scheduler comparison published |
| Steps | **20** | Steps comparison |
| CFG scale | **3.5** | CFG comparison |
| Seed | `2601892452` | Not deliberately varied |
| Style LoRA | **nyalia**, weight `0.6` | Fixed Signature Style Preset |

The author reports that the grids use the same Showcase-style configuration except for the parameter being compared. The supplied exported Showcase image contains **no readable generation metadata**, so these settings should not be presented as independently recovered from the image.

The **current daily-use settings** are different: regular portrait resolution **896 × 1152**, typically **30 steps**, CFG **3.5**, and a **WAI-Illustrious SDXL-family checkpoint above v15.0**. The older Showcase's *initial* resolution is not independently known from its exported file. See [`../configs/baseline.yaml`](../configs/baseline.yaml) for the historical record and [`../configs/personal-preferences.md`](../configs/personal-preferences.md) for current preferences.

## 1. Sampler — Euler / Euler a / Kohaku LoNyu Yog

![Euler, Euler a, and Kohaku LoNyu Yog](../examples/comparisons/sampler-comparison.jpg)

**Euler** produces some unexpected color patches along the hair edges and less clear layering. **Euler a** has messier hair highlights and shadows. Both show some character-structure issues. In this example, **Kohaku LoNyu Yog** gives the author's preferred overall result, with cleaner structure and more coherent shading.

Source of the preferred sampler: [Koishi-Star/Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler).

## 2. Sampling Steps — 5 / 10 / 15 / 20 / 30 / 40

![Sampling-step comparison](../examples/comparisons/steps-comparison.jpg)

Lower-step results are less resolved in parts of the illustration. Higher step counts alter fine details but do not yield a universally linear quality increase. The historical Showcase uses **20 steps**; **30 steps** is the author's current everyday preference.

## 3. CFG — 1.0 / 2.0 / 3.0 / 3.5 / 4.0 / 4.5 / 5.0 / 6.0

*The CFG comparison image is not yet in the GitHub repository. Planned location: `../examples/comparisons/cfg-comparison.jpg`.*

In this comparison, CFG values **below 3.5** appear grayer and lose some of the preferred style's detail. At **3.5 and above**, colors and contours become clearer, while increasing CFG further strengthens the outlines. The author prefers **CFG 3.5** as a balance; higher tested values can also work.

These are style-specific visual observations, not proof that CFG 3.5 is optimal in general.

## 4. ADetailer — Existing Initial Comparison

![Initial ADetailer comparison](../examples/comparisons/adetailer-comparison.jpg)

The repository **already contains** this initial comparison. The image is labeled with detector `None` on one side and `99coins_anime_girl_face_m_seg.pt` on the other, showing a contrast in the face-refinement configuration. A fully documented **ADetailer OFF vs ON** test would still require confirmation of the actual enabled state and recording the detector, mask, denoising, inpainting, and prompt settings.

**ADetailer is an optional refinement stage** of the NeoForge workflow, not a prerequisite for Myon_style.

## Planned Additions (Not Yet Fully Documented)

- Matched ADetailer OFF/ON test with a complete settings record
- Optional Hires.fix before/after comparison using a common source
- Additional Myon_style Showcase outputs
- Upload of the existing CFG grid to the documented image location

## Method Notes

When comparing one variable, keep the remaining adjustable parameters fixed as far as possible. A shared random seed across samplers does **not** guarantee identical compositions. Do not infer quantitative performance gains from these qualitative image grids, and do not confuse later personal settings with the historical Showcase baseline.

The separate personal **Myon_style LoRA** remains an **in-progress experiment**, not a source of the published grids.
