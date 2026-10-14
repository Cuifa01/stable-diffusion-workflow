# Planned and Current Comparisons

These images are personal visual examples, not statistical evidence or universal performance claims.

## Current examples

### Sampler preference

![Euler, Euler a, and Kohaku LoNyu Yog](../examples/sampler-comparison.jpg)

The grid compares Euler, Euler a, and Kohaku LoNyu Yog. Pose, composition, and details vary between panels, which limits direct attribution to the sampler. The author's practical preference is Kohaku LoNyu Yog + Karras for this style, especially for perceived line clarity, overall cleanliness, and visual appearance.

### Sampling steps

![5, 10, 15, 20, 30, and 40 steps](../examples/steps-comparison.jpg)

The grid shows the visible progression across the displayed step values. The author currently prefers 30 steps. This is a personal preference, not a quantitative or mathematical optimum.

### ADetailer

![ADetailer detector disabled and enabled](../examples/adetailer-comparison.jpg)

This supplied grid labels the left panel as detector `None` and the right panel with `99coins_anime_girl_face_m_seg.pt`. It is a useful example of the enabled/disabled configuration; further matched comparisons with complete settings are still planned.

## Planned comparisons

- **Normal vs Karras:** use the same sampler, prompt/style block, checkpoint, seed, dimensions, steps, CFG, and refinements; change only the scheduler.
- **ADetailer OFF vs ON:** record detector, confidence, mask, denoising, inpainting, and prompt settings; use matched source conditions.
- **Optional Hires.fix:** document the actual refinement method, scale, upscaler, denoising, and output dimensions; compare the same source image.
- **Additional Style Showcase Images:** add representative outputs from the same personal style workflow.

## Notes for future comparisons

Label the changed setting clearly, preserve source images and their metadata where appropriate, and describe what is visible in the actual images. A shared seed does not guarantee identical composition across different sampler trajectories. Avoid claims of universal superiority or numerical improvement unless future evidence supports them.
