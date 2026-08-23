# cw-tokens

Curious Ways design tokens. The only place a raw colour or type-scale
value may be written. Consumed by curiousways.com and projects.crwys.net.

Public: `github:curiousways/cw-tokens`. Font files stay in each consuming
repo — tokens name the family, they do not ship it.

Italic is licensed. Each consuming site ships `untitled-sans-italic.woff2`.
Do not italicise unless that file is loaded.

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

Weights shipped: 400, 500, 700. Italic 400 is licensed — each consumer
ships the woff2. Headings are 500. Tracking on headings is `−0.025em`.

## Colour

`@theme` wipes Tailwind's default colour map (`--color-*: initial`) so
only `cw-*` utilities compile. `transparent` is restored for
`focus:border-transparent` and `decoration-transparent`.

Neutrals are roles, not a numbered scale. Hex, not v4 oklch slate.
Do not derive the ladder with `color-mix()` or `oklch(from …)`.

| Role | Hex | Use |
| --- | --- | --- |
| `ink` | `#000` | Headings, chrome |
| `near-ink` | `#0f172a` | Near-black text |
| `strong` | `#1e293b` | Strong body |
| `body` | `#334155` | Default copy |
| `dim` | `#475569` | Secondary copy |
| `muted` | `#64748b` | Captions, meta |
| `subtle` | `#94a3b8` | Quiet labels |
| `rule` | `#cbd5e1` | Stronger rules |
| `line` | `#e2e8f0` | Hairlines |
| `panel` | `#f1f5f9` | Cards, bands |
| `wash` | `#f8fafc` | Page wash |
| `mist` | `#fafafa` | Warm-neutral wash (not `wash`) |
| `paper` | `#fff` | Surfaces |
| `quiet` | `#52525b` | Print / low-contrast chrome |
| `alert` | `#f87171` | Required asterisks, form errors |

Classes: `text-cw-body`, `bg-cw-panel`, `border-cw-rule`. Brand hues
stay named as they already were (`sunny-yellow`, `forest-green`, …).

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
