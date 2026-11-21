# visual standard

Canonical visual standard for SOSMLG repositories. Arabic translation: [THEME.ar.md](THEME.ar.md).

## palette

| role | hex | use |
| --- | --- | --- |
| canvas | `#16181D` | banners and dark surfaces |
| surface | `#202329` | nested panels |
| line | `#30343B` | borders and dividers |
| amber | `#E8A33D` | one highlight per view |
| amber muted | `#D2992F` | secondary accents where a theme needs them |
| text | `#D8D3C8` | body copy |
| muted | `#9A9AA2` | captions and labels |
| success | `#8FB57A` | passing status only |

## page rules

- Left align the page. Do not center the whole README.
- Say what the repo does in the headline. Remove hypewords and selling adjectives.
- Give the page one main action link. Do not stack buttons.
- Use a four-point grid of real statements. Each row must say something factual.
- Keep one bright moment: a single amber bar in the banner, or one active state. Flat surfaces everywhere else.
- Do not use gradients, gradient text, glow, glossy blobs, bouncing or any animation.
- Do not use emoji in headings, navigation, action links or cards.
- Do not use Inter for page or banner typography. Use the GitHub default for text and a monospace stack in SVG.
- Do not add stats cards, contribution graphs, pinned repository cards, badge walls or fake reviews.
- Do not write tiny all-caps captions or icon boxes.
- Engineering apps stay on their native light theme.
- Editors and terminals use Graphite Amber as the base theme. Optional legacy palettes may remain only in Linux theme pickers; they are not the default and are not used in docs, banners or badges.
- Do not add another color theme family or icon pack to docs, banners, badges, editors or terminals.
- English is canonical. Arabic is the only translation. No Chinese text.

## page layout

| part | rule |
| --- | --- |
| banner | flat graphite SVG, one amber bar, title and two factual lines |
| headline | one descriptive sentence, no adjectives that sell |
| action | one link, verb first, pointing to the quickstart or docs |
| grid | four rows, each a label and a real statement |
| detail | keep the existing technical sections below the grid |

Stats cards, streak cards, top-language cards and pinned repository cards are removed. Badge rows above the headline are removed.

## Windows profiles

- VSCodium: Graphite Amber custom colors on the built-in dark base, with an amber cursor and active border.
- Windows Terminal: Graphite Amber is the default and only scheme.
- Windows UI and engineering apps: native light, transparency off, reduced motion.
