# Example images — reserved slots

The author will provide the images later. The repository intentionally includes no invented comparison results.

| Filename to upload | Pair |
| --- | --- |
| `01-sampler-comparison.png` | Euler (Karras) vs Kohaku LoNyu Yog (Karras) |
| `02-scheduler-comparison.png` | Normal vs Karras, both Kohaku LoNyu Yog |
| `03-adetailer-comparison.png` | ADetailer off vs on, same base image and face crop |
| `04-hires-comparison.png` | Before vs after high-resolution refinement, same-image crops |

**Optional later:** `05-cfg-comparison.png`, `06-steps-comparison.png`, and a small SFW portrait gallery.

For every comparison, retain the **source PNG with generation metadata** where possible. Do not infer a refinement method from output resolution alone. If a final PNG lacks metadata, separately document the settings used.

Once each comparison exists, replace its corresponding `[Image placeholder]` line in the root `README.md` with a Markdown image reference such as:

```md
![Euler vs Kohaku LoNyu Yog](examples/01-sampler-comparison.png)
```
