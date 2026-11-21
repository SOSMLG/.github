# visual standard

This is the canonical visual standard for SOSMLG repositories. Arabic translation: [THEME.ar.md](THEME.ar.md).

## palette

| role | hex | use |
| --- | --- | --- |
| canvas | `#16181D` | banners, stats cards, dark surfaces |
| surface | `#202329` | terminal panels, nested cards |
| line | `#30343B` | borders, grids, dividers |
| amber | `#E8A33D` | titles, cursors, active borders, one highlight per view |
| amber muted | `#D2992F` | icons, secondary accents |
| text | `#D8D3C8` | body copy, terminal text |
| muted | `#9A9AA2` | captions, labels |
| success | `#8FB57A` | passing checks, quiet status only |

## rules

- Keep backgrounds graphite and low contrast. Avoid pure black and bright white.
- Use amber once per view. If the title is amber, keep borders muted.
- Keep body text warm gray. Never use neon gradients or glowing effects.
- Engineering apps stay on their native light theme.
- Editors and terminals use Graphite Amber as the base theme. Optional legacy palettes may remain only in Linux theme pickers; they are not the default and are not used in docs, banners, or badges.
- Do not add another color theme family or icon pack to docs, banners, badges, editors, or terminals. Optional legacy palettes already present in Linux theme pickers are exempt.
- Do not translate the palette names. Keep English canonical and Arabic as the only translation.
- Do not add Chinese text.

## GitHub cards

Use these query values for stats, top languages, and pinned repositories:

```text
bg_color=16181d
title_color=e8a33d
icon_color=d2992f
text_color=d8d3c8
border_color=30343b
```

Contribution streak cards use the same values with `theme=github_dark`. Badges use `style=for-the-badge` where practical.

## Windows profiles

- VSCodium: Graphite Amber custom colors on the built-in dark base, with an amber cursor and active border.
- Windows Terminal: Graphite Amber is the default and only scheme.
- Windows UI and engineering apps: native light, transparency off, reduced motion.
