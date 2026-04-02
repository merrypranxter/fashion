# Fashion Styles 1960–2000

A structured reference database of fashion styles, trends, and aesthetics from the early 1960s through the turn of the millennium — built for AI art generation, prompt engineering, and visual research.

Each style is decomposed into reusable, prompt-ready parts: silhouette, materials, palette, garments, accessories, grooming, and short token fragments for direct prompt injection.

---

## Quick Start

**For AI art prompts:** Use the `tokens` field in [`styles_index.yaml`](styles_index.yaml) for direct prompt injection, or mix `parts` across styles for hybrid looks.

**For visual research:** Follow `visual_examples` URLs to museum/archive records in each style entry.

**For influence mapping:** See [`meta/influence_graph.md`](meta/influence_graph.md) for documented style-to-style influence edges and hybrid prompt suggestions.

---

## Style Index (28 Movements)

All 28 core style movements in one machine-readable file:

→ **[`styles_index.yaml`](styles_index.yaml)** — master YAML with all style records

### 1960s
| Style | Years | Key Look |
|-------|-------|----------|
| [Beatnik-influenced couture](styles/beatnik_couture.md) | 1960–1962 | Slim dark tailoring; black leather; Left Bank minimalism |
| [Mod](styles/mod.md) | 1958–1966 | Geometric shift; color-blocked tights; precision bob |
| [Rude boy (ska era)](styles/rude_boy_ska_rocksteady.md) | 1962–1968 | Sharp suit; pork pie hat; slim tie |
| [Youthquake / Swinging London](styles/youthquake_swinging_london.md) | 1965–1968 | Micro-mini; Pop-art print; disposable novelty |
| [Space Age futurism](styles/space_age_futurism.md) | 1964–1968 | White go-go boots; architectural coatdress; silver |
| [Paper dress / Pop novelty](styles/paper_dress_pop_art.md) | 1966–1967 | Cellulose shift; Pop print as poster-wear |
| [Hippie / psychedelic bohemia](styles/hippie_psychedelic.md) | 1967–1973 | Afghan coat; patchwork suede; headband; earth tones |
| [Skinhead (first wave)](styles/skinhead_first_wave.md) | 1968–1971 | Close-cropped; polo + braces + heavy boots |

### 1970s
| Style | Years | Key Look |
|-------|-------|----------|
| [Glam rock](styles/glam_rock.md) | 1971–1975 | Platforms; glitter makeup; jumpsuit; theatrical androgyny |
| [Disco / nightlife glamour](styles/disco_glam.md) | 1974–1979 | Jersey sequin slink; Halston wrap; Studio 54 |
| [Punk](styles/punk.md) | 1976–1978 | Safety pins; bondage trousers; leather jacket; ripped tee |
| [Post-punk / New Wave](styles/post_punk_new_wave.md) | 1978–1983 | Thrift bricolage; art-school personal uniform |
| [Two-Tone ska revival](styles/two_tone_ska_revival.md) | 1979–1982 | Checkerboard suit; pork pie hat; monochrome |

### 1980s
| Style | Years | Key Look |
|-------|-------|----------|
| [New Romantic / Blitz scene](styles/new_romantic_blitz.md) | 1980–1984 | Theatrical DIY; pirate shirt; androgynous costume glamour |
| [Goth](styles/goth.md) | 1981–1995 | Black velvet + lace; pale base + dark lips |
| [Preppy / Ivy](styles/preppy_ivy.md) | 1980–1999 | Oxford + navy blazer; khaki; loafers |
| [Power dressing](styles/power_dressing.md) | 1983–1989 | Padded shoulders; double-breasted blazer; bold jewelry |
| [Aerobics / athleisure](styles/aerobics_athleisure.md) | 1981–1985 | Neon Lycra; leg warmers; leotard |
| [Japanese avant-garde / deconstruction](styles/japanese_avant_garde_deconstruction.md) | 1981–1999 | Black asymmetric; deconstructed volume |
| [Antwerp Six / Belgian avant-garde](styles/antwerp_six_belgian_avant_garde.md) | 1986–1999 | Concept garment; experimental textile |
| [Hip-hop streetwear](styles/hip_hop_streetwear.md) | 1979–1999 | Adidas tracksuit; gold chains; oversized; sneakers |
| [Acid house / rave](styles/acid_house_rave.md) | 1988–1992 | Neon baggy; smiley badge; bucket hat; motion-first |
| [Club kids / camp clubwear](styles/club_kids_camp_clubwear.md) | 1985–1996 | Extreme costume; body paint; nightlife spectacle |

### 1990s
| Style | Years | Key Look |
|-------|-------|----------|
| [Skate street style](styles/skate_street.md) | 1989–1999 | Baggy cargo; oversized tee; skate shoes |
| [Grunge](styles/grunge.md) | 1986–1994 | Flannel + ripped jeans + combat boots |
| [Minimalism (90s)](styles/minimalism_90s.md) | 1990–1999 | Clean column; neutral palette; quiet accessories |
| [Britpop / Madchester](styles/britpop_madchester_mod_revival.md) | 1990–1997 | Parka + polo; mod revival swagger |
| [Millennium futurism (Y2K)](styles/y2k_millennium_futurism.md) | 1998–2000 | Chrome + black; straps; tiny sunglasses |

---

## Repository Structure

```
fashion/
│
├── styles_index.yaml          # Master machine-readable style database (all 28 styles)
│
├── styles/                    # Individual style reference files
│   ├── beatnik_couture.md
│   ├── mod.md
│   ├── [... 26 more style files ...]
│   └── y2k_millennium_futurism.md
│
├── decades/                   # Decade overviews with style maps and palette forks
│   ├── 1960s.md
│   ├── 1970s.md
│   ├── 1980s.md
│   └── 1990s.md
│
├── meta/                      # Database metadata and context
│   ├── influence_graph.md     # Style influence edges; hybrid prompt suggestions
│   ├── timeline.md            # Chronological pivots and inflection points
│   └── sources.md             # Institutional source URLs and reference anchors
│
└── vocab/                     # Controlled vocabularies for prompt consistency
    ├── tokens.yaml            # Canonical token lists (silhouette, material, etc.)
    └── schema.yaml            # JSON Schema definition for style records
```

---

## How to Use This Database

### For AI Art Prompts

**Direct injection (fastest):** Use `tokens` from any style record in `styles_index.yaml`:
```yaml
# Example: grunge tokens
- "flannel + ripped jeans + combat boots"
- "thrift-layer anti-polish grunge"
- "Seattle scene bedhead layering"
```

**Composed prompts:** Combine `parts` fields for precision:
```
[silhouette] + [materials] + [palette] + [accessories] + [grooming] + [setting]
```

**Hybrid styles:** Use `meta/influence_graph.md` to find historically documented style combinations that are internally coherent.

### For Year-Accurate Prompts

Use `meta/timeline.md` to identify which style was dominant in a specific year. Important: many "1960s" images are actually mid-to-late 60s — the visual language changes significantly between 1964 and 1969.

### For Scene/Setting Context

Each style record includes `figures_media` (who/what anchors this look visually) and `visual_examples` (museum/archive URLs for reference images).

---

## Documented Influence Edges (Hybrid Prompt Pairs)

These combinations are historically grounded — the source styles actually influenced each other:

| Combination | Result |
|-------------|--------|
| punk + deconstruction | Distressed tailoring, anti-convention construction |
| mod + space age | Geometric minimalism + futurist materials |
| hip-hop + preppy | The Ralph Lauren recontextualization pattern |
| rave + skate | Baggy sportswear, function-first youth outdoors |
| new romantic + goth | Same post-punk London club origin |
| grunge + minimalism | 90s split-screen aesthetic |
| Japanese avant-garde + Belgian avant-garde | Concept garment territory |

Full influence graph: [meta/influence_graph.md](meta/influence_graph.md)

---

## Key Institutional Sources

| Source | URL | Best For |
|--------|-----|----------|
| FIT Fashion History Timeline | https://fashionhistory.fitnyc.edu/ | Decade overviews, year accuracy |
| The Metropolitan Museum of Art | https://www.metmuseum.org/art/collection | Object records, punk, designer histories |
| Victoria & Albert Museum | https://www.vam.ac.uk/collections/fashion | UK fashion, subcultures, photography |
| Museum at FIT exhibitions | https://www.fitnyc.edu/museum/exhibitions/ | Hip-hop, 90s fashion |
| MoMu Antwerp | https://www.momu.be/en/exhibitions | Belgian/Antwerp avant-garde |
| Museum of Pop Culture | https://www.mopop.org/collection | Grunge, Seattle scene |
| NMAAHC | https://nmaahc.si.edu/explore/stories | Hip-hop culture and fashion |
| Museum of Youth Culture | https://www.museumofyouthculture.com/ | Subcultures: goth, skinhead, rave, skate |

Full source list: [meta/sources.md](meta/sources.md)
