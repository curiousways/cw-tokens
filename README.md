# cw-tokens

Curious Ways design tokens. The only place a raw colour or type-scale
value may be written. Consumed by curiousways.com and projects.crwys.net.

Public: `github:curiousways/cw-tokens`. Font files stay in each consuming
repo — tokens name the family, they do not ship it.

Italic is not licensed yet. Do not italicise until Untitled Sans Italic
is added to the consuming site.

## Type

Live marketing scale. Change a variable here and both sites follow,
once they have pulled this package.

| Class | Role | Size |
| --- | --- | --- |
| `.t-heading-mega` | Page titles, hero | 36 → 48 → 60px |
| `.t-heading-med` | Section / card headings | 24px |
| `.t-heading-sml` | Mini titles | 16 → 20px |
| `.t-heading-micro` | Footer labels, metadata | 16px |
| `.t-lead` | Standfirst after a title | 18 → 20px |
| `.t-body` | Default paragraph | 16px |
| `.t-caption` | Legal, as-of, captions | 14px |

`--text-fine` (12px) is the kicker / small-caps size. No class — compose
it in the component.

Weights shipped: 400, 500, 700. Headings are 500. Tracking on headings
is `−0.025em`.

## Prefix taxonomy

| Prefix | Role |
| --- | --- |
| `l-` | Layout — containers, stacks, grids |
| `t-` | Typography — the type scale |
| `c-` | Component — one file per component |
| `u-` | Utility — project one-offs Tailwind does not provide |
| `is-` | State / CMS-authored content (rich text, form fields) |

BEM for elements and modifiers: `c-masthead__logo`, `c-step--done`.

Custom classes are plain CSS referencing these variables. Do not `@apply`
a `t-` or `c-` class.

## Install

```
"cw-tokens": "github:curiousways/cw-tokens"
```

Then `@import "cw-tokens/tokens.css";` from the site stylesheet.

After a token change: publish this repo, then update the dependency on
each consumer and deploy both.
