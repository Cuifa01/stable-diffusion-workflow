# Prompt Structure

This document records my personal prompt-writing layout for **Stylized Anime Portrait Generation Workflow**. It separates scene-specific inputs from a fixed visual style preset so that camera framing, gestures, expressions, clothing, and background can be edited independently.

## Six-part layout

After a short quality-tag preamble, I organize the positive prompt with `BREAK` into six functional sections:

1. **Camera and composition** — framing and viewpoint (for example, `portrait`, `upper body`, `close-up`).
2. **Pose and action** — gesture, body position, and direction of attention.
3. **Character and expression** — character identity, face, and mood.
4. **Body and outfit** — appearance and clothing.
5. **Fixed style preset** — the artist-tag combination and `nyalia` style LoRA, kept together as one block.
6. **Background** — minimal graphic elements and simple color fields.

The placeholders in this outline are instructions for editing, **not literal tags to paste into NeoForge**.

```text
masterpiece,best quality,highres,newest,
(ultra detailed:1.08),detailed face,beautiful color,sfw,
BREAK
[1. Camera and composition]
BREAK
[2. Pose and action]
BREAK
[3. Character and expression]
BREAK
[4. Body and outfit]
BREAK
artist:tianliang duohe fangdongye,(kanpa \(campagne 9\):0.8),(alpha \(alpha91\):0.6),(koyama shigeru:0.6),(massakasama:0.55),
<lora:nyalia:0.6>,
BREAK
[6. Background]
white border,simple background,
```

See [`../style/signature-style.txt`](../style/signature-style.txt) for the standalone fixed style block and [nyalia (Illustrious)](https://civitai.com/models/834822/nyalia-illustrious) for the referenced LoRA.

## Example positive prompt

The following is the **complete positive prompt supplied by the author**, with the original tags, weights, `BREAK` separators, and ordering preserved.

```text
masterpiece,best quality,highres,newest,
(ultra detailed:1.08),detailed face,beautiful color,sfw,
BREAK
portrait,upper body,close-up,
BREAK
dynamic pose,
legs apart,v,one eye closed,hand on own hip,leaning forward,
looking at viewer,
BREAK
konpaku youmu,konpaku youmu \(ghost\),
blush,body blush,shiny skin,smile,open mouth,
BREAK
white shirt,short sleeves,green pleated skirt,
slender,
BREAK
artist:tianliang duohe fangdongye,(kanpa \(campagne 9\):0.8),(alpha \(alpha91\):0.6),(koyama shigeru:0.6),(massakasama:0.55),
<lora:nyalia:0.6>,
BREAK
white border,simple background,pink background,
```

## Example negative prompt

```text
western comics \(style\),realistic,nsfw,text,
extra digits,extra toes,bad feet,lowres,jpeg artifacts,bad anatomy,bad hands,worst quality,low quality,signature,watermark,blurry,cropped,multiple views,anthro,chibi inset,monochrome,boldline,
body hair,pubic hair,wrinkled skin,fat rolls,
```

## Usage notes

- Keep the fixed style block together when changing the subject, composition, pose, or background.
- The six categories make the prompt easier to edit and document; they do **not** guarantee independent control of every visual attribute.
- The example above is an author-provided prompt. It should not be presented as independently recovered from the published Showcase PNG, whose exported copy lacks readable generation metadata.
- This version documents the combined style preset as a single configuration, without individual artist-tag ablation or attribution.
