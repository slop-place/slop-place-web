# slop.place

The site behind [slop-place](https://github.com/slop-place) — an org that
publishes software written end to end by AI, with the numbers to check it by.

Static: one HTML file, one stylesheet, no build step, no JavaScript.

## Design

The ground is institutional canteen green, because "slop" is the brief and a
melamine tray is where slop lives. The signature is the **Slop Facts** panel: a
software release presented as a regulatory nutrition label, set with the real
thing's typographic rules — thick, medium and hairline dividers, tight leading,
numbers hard right. Every figure on it is true and checkable in the repository
it describes.

| Role | Value |
|---|---|
| Tray (page ground) | `#7E9068` |
| Tray, in shadow | `#6C7C59` |
| Under the counter | `#4A5640` |
| Label stock | `#F7F4EA` |
| Ink | `#171A11` |
| Slop highlight | `#A8CE7B` |

Display and body are [Archivo](https://fonts.google.com/specimen/Archivo) —
an American grotesque drawn for signage and small print, which is the right
reference for a regulatory panel. Data is set in IBM Plex Mono.

## Local

```sh
python3 -m http.server 8787
```

Then open http://127.0.0.1:8787.

## Deploying

Cloudflare Pages, serving the repository root. There is no build command and no
output directory to configure.

```sh
npx wrangler pages deploy . --project-name slop-place
```

Or connect the repository in the Cloudflare dashboard and leave the build
settings empty.
