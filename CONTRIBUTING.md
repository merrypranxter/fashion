# Contributing to `fashion`

This repository is a structured reference of late 20th‑century fashion movements, designed first for AI art/prompt systems and second for human browsing.[cite:2][cite:3]

The goal of any contribution is to keep the data:
- Historically grounded (anchored to real scenes, garments, subcultures).
- Prompt‑ready (short, composable phrases instead of prose descriptions).[cite:11][cite:12]
- Consistent with the existing schema in `vocab/schema.yaml` and the styles in `styles_index.yaml`.[cite:3][cite:11]

## Adding or editing a style record

Style records live in two places:
- `styles_index.yaml` — machine‑readable list of all styles (source of truth).[cite:3]
- `styles/<style_id>.md` — human‑readable reference page for a single style.[cite:7]

When you add or refine a style:
- Choose a short `id` in `snake_case` that matches the existing naming pattern.
- Add a full record in `styles_index.yaml` that conforms to the `StyleMovement` schema in `vocab/schema.yaml`.
- Include:
  - `aka` with common aliases and search terms.
  - `years` with approximate start/end of the style.
  - `origin` with regions/cities.
  - `influences` with culture and music anchors where relevant.
  - `parts` broken into `silhouette`, `materials`, `palette`, `garments`, `accessories`, and `grooming`.
  - `designers_brands`, `figures_media`, and at least one or two `tokens`.
  - 2–4 `visual_examples` pointing to museum, archive, or institutional image records.

Then, create or update the corresponding `styles/<id>.md` page using one of the existing files (for example `styles/grunge.md` or `styles/y2k_millennium_futurism.md`) as a template.

### Historical and visual sources

- Favor institutional collections, museum exhibitions, or long‑running archives.
- Use street and youth‑culture archives for subcultural scenes (skate, rave, club kids, etc.).[cite:4][cite:5]
- Avoid linking to short‑lived image hosts or low‑context social media posts.

## Working with vocabularies

The `vocab/` directory defines shared tokens and shapes how prompts are assembled:[cite:6]
- `vocab/schema.yaml` — the JSON‑style schema for each style record.[cite:11]
- `vocab/tokens.yaml` — canonical building blocks for silhouettes, materials, patterns, accessories, grooming, and settings used across styles.[cite:12]

When extending vocab:
- Prefer adding new items under existing categories instead of inventing new top‑level keys.
- Keep tokens short, descriptive, and directly usable in prompts (no long sentences).
- Avoid duplicating terms that already exist under a slightly different phrasing.

If you need new domains of tokens (for example, camera or lighting language), consider adding a dedicated vocab file such as `vocab/camera_lighting_tokens.yaml` rather than overloading `tokens.yaml`.

## Decade and meta files

The `decades/` and `meta/` directories hold context and wiring documents:
- `decades/*.md` give decade overviews and style maps.[cite:4]
- `meta/influence_graph.md` documents historically grounded connections between styles.[cite:5]
- `meta/timeline.md` helps with year‑accurate prompting across overlapping movements.[cite:5]
- `meta/sources.md` collects institutional references.[cite:5]

When editing these files:
- Keep tables and lists machine‑parseable where possible.
- Only add influence edges or timeline events that can be backed with at least one credible source.

## Prompt‑oriented additions

If you want to add usage guides rather than new data, good candidates include:
- How to compose prompts from `parts` and `tokens`.
- Model‑agnostic tips for mixing movements from `styles_index.yaml`.
- Guidance for keeping looks chronologically coherent (for example, avoiding 1970s hair on a 1999 Y2K silhouette).

These belong under `meta/` (for example, `meta/prompt_playbook.md`).

## Style and formatting

- Use Markdown for human‑facing files.
- Use YAML for data files and keep keys aligned with the existing schema.
- Wrap style names and file paths in backticks when they appear inline.
- Keep line lengths reasonably short (around 80–100 characters) to ease diffing.

## Opening pull requests

When you open a PR:
- Briefly describe which styles or files you touched.
- Call out any new IDs you introduced.
- Mention any new vocab domains so downstream tools can be updated.

This project is meant to be a stable, inspectable reference — small, precise contributions are preferred over sweeping rewrites.
