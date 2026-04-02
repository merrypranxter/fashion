# Prompt Playbook for `fashion`

This playbook shows how to turn the structured data in this repo into practical prompts for AI image or video models, without being tied to any specific tool.[cite:2][cite:3]

It assumes you are pulling building blocks from:
- `styles_index.yaml` and the `styles/` pages.[cite:3][cite:7]
- `vocab/tokens.yaml` for silhouettes, materials, accessories, grooming, and settings.[cite:12]
- Optional camera and lighting vocab from `vocab/camera_lighting_tokens.yaml` if present.[cite:11]

## Anatomy of a fashion prompt

Most fashion prompts in this ecosystem can be decomposed into:

- Style anchor (one or two movements).
- Time/place anchor (decade and scene).
- Body and clothes (silhouette, garments, materials, palette).
- Accessories and grooming.
- Setting, camera, and lighting.

A generic text layout might look like:

> `[movement label]` fashion, `silhouette` silhouette, `materials` in `palette` palette, `garments` with `accessories`, `grooming`, shot in `setting` as a `camera_framing` with `lighting_style` lighting

Where the quoted fragments come from the YAML fields and vocab files.

## Example prompts by movement

### Grunge street portrait

- Style: `grunge`.
- Parts: flannel + ripped jeans + combat boots; thrift layers; bedhead grooming.[cite:3][cite:12]
- Setting: Seattle alley or small venue stage.

Example prompt:

> 1992 Seattle grunge street style, loose layered silhouette, flannel, ripped jeans and combat boots in plaid earth‑tone palette, unkempt bedhead hair and minimal makeup, shot in a damp back‑alley near a venue, three‑quarter street portrait, soft overcast light

### Y2K millennium futurism club scene

- Style: `y2k_millennium_futurism`.
- Parts: chrome + black techwear straps; tiny sunglasses; sleek hair.[cite:3][cite:12]
- Setting: nightlife club or rooftop bar.

Example prompt:

> 1999 Y2K millennium futurism look, sleek cropped low‑rise silhouette with chrome and black technical fabrics, strappy micro top and low‑rise pants, tiny sunglasses and glossy lip, in a chrome‑and‑glass rooftop club, full‑body fashion shot with hard mixed neon lighting

### 80s power dressing editorial

- Style: `power_dressing`.
- Parts: padded‑shoulder blazer, pencil skirt, bold jewelry.[cite:3]
- Setting: corporate tower or boardroom.

Example prompt:

> 1986 power‑dressing editorial, broad‑shouldered tailored blazer and pencil skirt in navy and black with bold gold jewelry, clean polished hair and professional makeup, posed in a glass‑and‑steel office tower lobby, three‑quarter editorial shot on 85mm lens, soft studio key light with subtle rim light

## Mixing movements coherently

The influence graph in `meta/influence_graph.md` documents historically grounded hybrids that already make sense in the real record — for example, punk + deconstruction, mod + space age, hip‑hop + preppy, rave + skate, new romantic + goth, and grunge + 90s minimalism.[cite:2][cite:5]

When mixing styles:
- Keep one movement as the structural base (silhouette and core garments).
- Let the second movement contribute materials, palette, or accessories.
- Use decade and scene to keep the combination believable.

Example (punk + deconstruction):

> late‑70s deconstructed punk look, strapped and ripped tailoring in black and red tartan with exposed seams, safety‑pin hardware and chains, pale base with dark eyeliner, shot in a cramped club stage setting with harsh on‑camera flash

## Year‑accurate prompts

Use `meta/timeline.md` and the decade files under `decades/` to align looks with the right year range and social context (for example, early‑70s hippie vs late‑70s disco; early‑80s New Romantic vs mid‑80s power dressing).[cite:4][cite:5]

Tips:
- Decide the exact year (or 2–3 year window) you want to evoke.
- Pick only styles that are active in that span.
- Avoid mixing silhouettes that never overlapped (for example, 1966 paper‑dress novelty with 1999 Y2K techwear).

## Camera and lighting language

If you add `vocab/camera_lighting_tokens.yaml`, you can pull:
- Framing tokens like `full‑body runway shot`, `three‑quarter editorial portrait`, `tight beauty close‑up`.
- Lens tokens like `35mm street shot`, `50mm normal perspective`, `85mm shallow‑depth portrait`.
- Lighting tokens like `soft studio key`, `hard on‑camera flash`, `golden‑hour backlight`, `moody club strobe`.

These can be appended to any movement‑based prompt to nudge composition without changing the clothes.

## Scenes and settings

The `setting_tokens` section in `vocab/tokens.yaml` gives ready‑made backdrops such as `Carnaby Street boutique`, `warehouse rave`, `Studio 54 dance floor`, `downtown skate spot`, and `Tokyo avant‑garde space`.[cite:12]

Use them to:
- Reinforce the origin city/region when possible.
- Anchor subcultural looks in the right scene (dancefloor vs street vs runway).
- Push variety by swapping scenes while keeping the same outfit.

## Working with video models

For video or motion prompts:
- Start with the same outfit description as for still images.
- Add verbs and motion cues (for example, walking down a runway, dancing in a crowded club, skating a curb).
- Keep the camera and lighting language, but add movement cues such as `handheld`, `tracking shot`, or `slow dolly in`.

The underlying style data remains the same; only the verbs and motion language change.

---

This file is deliberately model‑agnostic so it stays useful even as specific AI systems change. Treat it as a starting point and adapt wording to whatever renderer you are using.
