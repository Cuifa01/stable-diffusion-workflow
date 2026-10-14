# Stylized Anime Portrait Generation Workflow

A practical, reproducible **Stable Diffusion NeoForge** workflow for **Cute Anime Portrait / Soft Cel Shading / Clean Line Art / Minimal Graphic Background**.

> **Status:** Work in progress. Configuration notes are based on the author's real usage; controlled comparison images and results will be added later. This is a personal workflow documentation project, not a claim of developing a new diffusion model or sampler.

## Scope

- Character-focused anime illustrations with simple graphic backgrounds
- A stable, documented style configuration (treated as a single combined style; individual artist-tag effects are **not** analyzed here)
- Sampler and scheduler preferences
- Face refinement with ADetailer
- High-resolution refinement
- Reproduction notes and known limitations

## Selected workflow

| Component | Current preference | Notes |
| --- | --- | --- |
| Interface | Stable Diffusion WebUI NeoForge | Workflow interface |
| Checkpoint | `reedXXXIllustrious_v160` | From one source image's embedded metadata; hash `dd984164e4` |
| Sampler | **Kohaku LoNyu Yog** | Provided by [Koishi-Star/Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler) |
| Scheduler | **Karras** | Personal visual preference; comparison pending |
| Sampling steps | **30** | A recorded setting, not an established universal optimum |
| CFG scale | **3.5** | A recorded setting, not an established universal optimum |
| Style | Soft cel-shaded cute anime portraits | Style prompt treated as one fixed block |
| Face refinement | ADetailer | Targeted facial refinement; comparison pending |
| Resolution refinement | Used in the author's broader workflow | Specific method/settings to be documented |

> The upstream Kohaku sampler README recommends 10 steps and describes the method as second order and slower; **30 steps is this workflow's recorded setting**, not the upstream recommendation. Compare quality and runtime before making a broader claim.

## Comparison gallery (images pending)

### 01 — Sampler: Euler vs Kohaku LoNyu Yog

**Controlled:** checkpoint, full prompt/style block, LoRA, seed, steps, CFG, resolution, Karras scheduler. Disable downstream refinements for this comparison.

**[Image placeholder: `examples/01-sampler-comparison.png`]**

Result / observations: **TODO — to be written after generating matched examples.**

### 02 — Scheduler: Normal vs Karras

**Controlled:** checkpoint, prompt/style block, LoRA, seed, steps, CFG, resolution, Kohaku LoNyu Yog sampler. Disable downstream refinements.

**[Image placeholder: `examples/02-scheduler-comparison.png`]**

Result / observations: **TODO.**

### 03 — ADetailer: off vs on

Use the **same generated base image** and a matching face crop to show what targeted face refinement changes.

**[Image placeholder: `examples/03-adetailer-comparison.png`]**

Result / observations: **TODO.**

### 04 — High-resolution refinement: before vs after

Show the **same source image** before/after processing, plus a same-area detail crop displayed at a comparable size. Record the exact method and scale.

**[Image placeholder: `examples/04-hires-comparison.png`]**

Result / observations: **TODO.**

## Documentation

- [Workflow and configuration](docs/workflow.md)
- [Fair comparison protocol and image slots](docs/comparisons.md)
- [Image upload checklist](examples/README.md)
- [Recorded starting configuration](configs/baseline.yaml)

## Limitations

The author has observed that the preferred checkpoint often benefits from additional face refinement and is less reliable for highly detailed backgrounds. These are **personal observations**, not benchmark-proven limitations of every model or prompt. The comparison gallery will distinguish observed outcomes from broader claims.

## Credits and redistribution

Sampler: [Koishi-Star/Euler-Smea-Dyn-Sampler](https://github.com/Koishi-Star/Euler-Smea-Dyn-Sampler). Check upstream repositories for installation, licenses, and version compatibility. Model and LoRA weights are **not** redistributed here. Only appropriately licensed, SFW demonstration images should be uploaded.
