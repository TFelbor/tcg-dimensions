# TCG & board-game dimensions: sleeves, deck stacks and box interiors

A small open dataset of card, sleeve and game-box dimensions for designing organizers
for trading card games and board games: deck boxes, inserts and trays. **Every value
says where it came from.** It was built by the Daedal Studio team in 2026 for a
parametric deck-box engine that had to be right to the millimetre, and it's published
under CC BY 4.0 now that the company has closed.

## What's in it

| File | Contents |
|---|---|
| `data/sleeves.v1.json` / `.csv` | Standard card size; the outside size of a sleeved card for unsleeved, single, double and thick-inner double sleeving; and the **design pitch per card** (how thick to plan each card in a stack). |
| `data/game_boxes.v1.json` / `.csv` | Interior dimensions of three boxes: Wingspan, Ultimate Guard Boulder 100+, and a DeckSmith Commander box. Each axis has its own source, basis and capture date. |
| `docs/dimension-kb-research.md` | The full research note: card sizes, per-layer sleeve thickness by brand (stated vs measured), sleeved footprints and clearances, dice, what existing parametric generators default to, FDM tolerance reality, and why no public game-box database exists. |

## The findings people usually get wrong

- **100 double-sleeved cards measure 66–67 mm**, not the 72–80 mm that forum rules of
  thumb suggest. This is based on two independent caliper measurements. We design at
  0.70 mm per card, which includes an air margin.
- **Published sleeve thicknesses differ from caliper readings by 8–25 % per sleeve.**
  The research note gives the figures per brand.
- **No public database of game-box *interiors* exists.** BoardGameGeek lists external
  dimensions only, user-entered and in inches. That's why this dataset is small and
  sourced, rather than big and guessed.

## Provenance vocabulary

Every value in `game_boxes` carries a `basis`:

- `spec`: published by the maker;
- `measured`: a caliper measurement someone reported, with the source linked;
- `derived`: computed from other values, and it must carry a `note` saying how.

Rules of thumb ("folk" values) are deliberately not accepted as data.

`captured_on` is the date the value was transcribed, not the date it was measured.

## Contributing a measurement

This dataset isn't maintained. If you fork it, keep the rule that made it useful:
**no value without a source**, and say whether it was measured or derived.

## Licence and citation

- **Licence:** data and documentation are licensed under
  [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
- **Third-party sources:** individual measurements are facts reported by the linked
  sources. We credit them, and their pages remain theirs.
- **Attribution:** "TCG & board-game dimensions, Daedal Studio (Tytus Felbor, Alberto
  García de la Torre, Brandon Perrone), 2026, CC BY 4.0". See `CITATION.cff`.

The parametric engine that used this data is archived at https://github.com/TFelbor/daedal-studio. The story
of the company is at (https://substack.com/@tytusfelbor).
