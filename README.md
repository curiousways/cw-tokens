# cw-tokens

Curious Ways design tokens. Consumed as a git dependency by every CW
front end (curiousways.com, projects.crwys.net, and anything that follows).

**This repo is the only place a raw colour value may be written.**

The first `@theme` block is the canonical copy from curiousways.com.
A second block names the neutrals both sites already used as raw hex
(ink, paper, muted, body, line, wash). Those names are not yet on the
marketing site — confirm them before treating them as canonical.

Font files stay in each consuming repo — tokens name the family, they
do not ship it.

## Prefix taxonomy

| Prefix | Role |
| --- | --- |
| `l-` | Layout — containers, stacks, grids |
| `t-` | Typography — the type scale |
| `c-` | Component — one file per component |
| `u-` | Utility — project one-offs Tailwind does not provide |
| `is-` | State / CMS-authored content (rich text, form fields) |

BEM for elements and modifiers: `c-masthead__logo`, `c-step--done`.

Custom classes are plain CSS referencing theme variables. Do not `@apply`
a `t-` or `c-` class.

## Install

```
"cw-tokens": "github:curiousways/cw-tokens"
```
