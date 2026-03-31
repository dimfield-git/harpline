# Harmonica Reference

**[→ Open the live app](https://dimfield-git.github.io/harpline/)**

Interactive reference tool for 10-hole Richter diatonic harmonicas. A single self-contained HTML file — no build step, no dependencies, no server.

Covers positions 1–3 with note maps, scale degrees, triads, position lookups, and scale patterns for five harp keys: **Low F**, **C**, **D**, **G**, and **A**.

## Features

**Note Map** — Full blow/draw/bend layout for the selected harp, displayed both as an interactive graphic and a detailed table. Every note shows its scale degree relative to the harp key.

**Universal Degree Map** — The Richter tuning pattern that's identical across all keys. Blow degrees, draw degrees, and bend functions for every hole.

**Triads** — All seven diatonic triad shapes plus the octave, shown as hover-interactive cards and a reference table. Patterns are universal; notes update per harp.

**Positions** — 1st, 2nd, and 3rd position anchor keys for each harp, with a cross-reference table showing which harp to grab for any target key.

**Scales** — Scale patterns for all three positions, organized in two columns with a color-coded harp strip diagram above each section. Each token shows the scale degree, note name, and hole notation stacked vertically. Includes:

| Position | Scales |
|----------|--------|
| 1st | Major pentatonic, full major |
| 2nd | Major pentatonic, full major, minor pentatonic, blues, mixolydian (both octaves) |
| 3rd | Major pentatonic, full major, minor pentatonic, blues, natural minor, dorian |

## Themes

Five color themes, switchable at any time:

- **Energikalkyl** — warm green and amber on cream (default)
- **Blueprint** — teal and slate on light grey
- **Midnatt** — blue and gold on dark navy
- **Grafit** — green and amber on dark charcoal
- **Konstruktivist** — red and cream on black

## Usage

Open `harmonica_reference.html` in any modern browser. That's it.

Select a harp key and a theme from the chips in the header. Navigate between views using the tab bar. Everything runs client-side with zero network requests (aside from Google Fonts on first load).

## Notation

| Symbol | Meaning |
|--------|---------|
| `4` | Blow hole 4 |
| `-4` | Draw hole 4 |
| `-3'` | Draw bend ½ step |
| `-3''` | Draw bend whole step |
| `-3'''` | Draw bend 1½ steps |
| `5*` | Overblow hole 5 |

## Technical notes

- Single HTML file, ~700 lines. All CSS, JS, and data inline.
- No framework. Vanilla JS with a simple state → render cycle.
- Responsive down to mobile widths.
- Fonts loaded from Google Fonts: JetBrains Mono, Literata, DM Sans.
- Note resolution and degree calculation done chromatically at render time — adding a new harp key only requires adding its data object.

## Adding a harp key

Add an entry to the `HARPS` object in the `<script>` block following the existing pattern. Each harp needs: `tonic`, `label`, `notes` (array of 10 holes with blow/draw/bends), `triads` (8 entries), and `pos` (position keys for 1st/2nd/3rd). Then add the key string to the `HARP_KEYS` array.

Scale patterns in the `SCALES` object are universal and don't need to change — note resolution is automatic.

## License

MIT
