---
# HOW TO ADD A RESEARCH PAGE
# 1. Copy this file to _research/<slug>.md (lowercase, no spaces). The page will live at /research/<slug>/.
#    (Files starting with "_" — like this one — are ignored by Jekyll.)
# 2. Put the hero image in assets/images/ (wide, ~1900x800, dark with the subject on the right works best).
# 3. Fill in the fields below. Only title, description, date, and image are required.
# The page automatically shows up on the /research/ hub, as a tile on the home page, and under
# "More Research" on every other research page. Add a "Project page" link to its entry in publications.md.

title: PROJECT NAME                     # big title in the hero and on cards
short_title: NAME                       # label under the home-page tile (keep it to one or two words)
subtitle: "One-line tagline that says what it does."
description: "Two-sentence pitch. Used on the /research/ card and as the Google / social-media description."
date: 2026-01-01                        # ordering only (newest first); never displayed
image: /assets/images/PROJECT-hero.webp # hero background, card thumbnail, and social-media preview image
hero_position: right center             # CSS background-position for the hero
thumb: /assets/images/PROJECT-thumb.jpg # optional 16:9 card image (~960x540) with the subject centred; the
                                        # home tile uses its centre. Without it, cards/tiles crop `image` at:
thumb_position: 50% 50%                 # focus point for those crops (x% y%), used only when there is no `thumb`
# icon: /assets/images/PROJECT-icon.png # optional square logo for the home tile (otherwise a crop of `image`)

venues:                                 # small pills above the title; first one also shows under the tile
  - label: VENUE 2026
    note: Rank A*                       # optional
    url: https://arxiv.org/pdf/XXXX.XXXXX  # optional

links:                                  # hero buttons; the first is styled as the primary action
  - label: Read the Paper
    url: https://arxiv.org/pdf/XXXX.XXXXX
    icon: paper                         # paper, code, library, talk, video, monitor, engine, award, link
  - label: Code
    url: https://github.com/Offensive-AI-Lab/REPO
    icon: code

authors:                                # names matching a member page (/first.last/) are linked automatically
  - First Last
  - Yisroel Mirsky

topics: [AI Security]                  # the lab's research areas: AI Security, AI Safety, Attacks Using AI.
                                        # Shown as chips and used by the hub's topic filter; keep to this short list.

bibtex: |                               # optional "Cite This Work" box with a copy button
  @inproceedings{lastname2026key,
    title     = {...},
    author    = {...},
    booktitle = {...},
    year      = {2026}
  }

# featured_in: WIRED                    # optional "Featured in ..." badge on the /research/ card
funding: erc                            # optional funding notice at the bottom: erc, microsoft, or [erc, microsoft]
---

## The Problem

Write the page body in normal Markdown. Each `##` heading becomes a section.

## How It Works

Reusable building blocks (see _research/gavel.md for live examples):

- `<video class="rmedia" autoplay loop muted playsinline>` for a demo clip
- `<div class="rflow">` with `rflow-step` / `rflow-arrow` children for a pipeline diagram
- `<div class="rfeatures">` with `rfeature` cards for tools, datasets, or releases
- `<div class="rvideo"><iframe ...></iframe></div>` for a responsive YouTube embed
