# slop.place

The site behind [slop-place](https://github.com/slop-place) — an org that
publishes software written end to end by AI, with the numbers to check it by.

Static: one HTML file, one stylesheet, no build step, no JavaScript.

## What is on the counter

Servings are newest first, each with its own Slop Facts panel.

| Project | What it is |
|---|---|
| [runnerforge](https://github.com/slop-place/runnerforge) | Ephemeral CI runners: one throwaway machine per job, for GitHub Actions, GitLab CI and Forgejo, on any cloud — [detail page](/runnerforge) |
| [terraform-provider-mattermost](https://github.com/slop-place/terraform-provider-mattermost) | A Terraform provider for Mattermost: teams, channels, users, bots, integrations and the system configuration |
| [terraform-provider-freshdesk](https://github.com/slop-place/terraform-provider-freshdesk) | A Terraform provider covering the whole of the Freshdesk API v2 |

A project with more to show gets its own page: a copy of the Slop Facts panel,
then `<figure class="shot">` blocks pairing a screenshot with what it is
demonstrating. Screenshots wear the label's own border and hard shadow, so they
read as another thing served on the same tray rather than as floating images.

Adding one to the index means a new `<section class="serving">` in `index.html`. Alternate
`serving--alt` on every other section so a stack of them reads as separate
dishes rather than one long panel.

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
