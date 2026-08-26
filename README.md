# cw-tokens

Curious Ways design tokens. The only place a raw colour or type-scale
value may be written. Consumed by curiousways.com and projects.crwys.net.

Public: `github:curiousways/cw-tokens`. Font files stay in each consuming
repo — tokens name the family, they do not ship it.

Italic is licensed. Each consuming site ships `untitled-sans-italic.woff2`.
Do not italicise unless that file is loaded.

## Entry points

| Import | What it is |
| --- | --- |
| `cw-tokens` / `cw-tokens/tokens.css` | Raw tokens. Plain `:root`. Framework-free. |
| `cw-tokens/tailwind.css` | Tailwind adapter. Maps names only. No hex. |

Tailwind sites import both, raw first:

```
@import "cw-tokens/tokens.css";
@import "cw-tokens/tailwind.css";
```

`--cw-ink` is the token. `--color-cw-ink` is the alias that generates
`bg-cw-ink` / `text-cw-ink`. Do not write a hex in the adapter. Adding a
colour is two adjacent lines: the value in `tokens.css`, the alias in
`tailwind.css`.

`--font-untitled-sans` stays the Tailwind-facing font name
(`font-untitled-sans` on `<body>`). Its value is `var(--cw-font-sans)`.

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

`--text-fine` (12px) is the kicker / small-caps size. `--text-nano` (10px)
is chips and pill labels. No class — compose them in the component.

These `--text-*` names collide with Tailwind v4's font-size namespace.
They stay in plain `:root`. Do not move them into the adapter.

Weights shipped: 400, 500, 700. Italic 400 is licensed — each consumer
ships the woff2. Headings are 500. Tracking on headings is `−0.025em`.

## Colour

Raw names are `--cw-*`. The adapter wipes Tailwind's default colour map
(`--color-*: initial`) so only `cw-*` utilities compile. `transparent`
is restored for `focus:border-transparent` and `decoration-transparent`.

Neutrals are a position on the ink-to-paper ramp. Hex, not v4 oklch slate.
Do not derive the ladder with `color-mix()` or `oklch(from …)`.

| Token | Hex |
| --- | --- |
| `ink` | `#000` |
| `ink-strong` | `#1e293b` |
| `ink-mid` | `#334155` |
| `ink-dim` | `#475569` |
| `ink-muted` | `#64748b` |
| `ink-subtle` | `#94a3b8` |
| `ink-faint` | `#cbd5e1` |
| `ink-ghost` | `#e2e8f0` |
| `paper-sunk` | `#f1f5f9` |
| `paper-soft` | `#f8fafc` |
| `paper` | `#fff` |

Accents off the ramp: `orange-ink` `#9a3412`, `green-tint` `#ecfdf5`,
`alert` `#f87171`.

Classes: `text-cw-ink-mid`, `bg-cw-paper-sunk`, `border-cw-ink-faint`.
Brand hues stay named as they already were (`sunny-yellow`, `forest-green`, …).

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

Then import both files from the site stylesheet, raw first.

After a token change: publish this repo, then update the dependency on
each consumer and deploy both.
