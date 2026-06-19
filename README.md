# HackUTD Docs

The centralized documentation for [HackUTD](https://hackutd.co)'s open source projects, built with [Mintlify](https://mintlify.com) and served at [docs.hackutd.co/docs](https://docs.hackutd.co/docs).

## Repository structure

| Path | Description |
| --- | --- |
| `docs.json` | Site config: navigation, theme colors, logos, navbar, footer. |
| `index.mdx` | Landing page (intro + project cards). |
| `jury.mdx`, `harp.mdx`, `technical-documentation.mdx` | Project pages. |
| `style.css` | Brand theme: HackUTD gradient, Satoshi font, buttons. Auto-loaded by Mintlify. |
| `logo/` | `light.svg` (dark wordmark) and `dark.svg` (white wordmark). |
| `favicon.svg` | Black HackUTD mark. |
| `cloudflare-worker.js` | Reverse proxy that serves the docs under the `/docs` subdirectory. |

## Local development

Install the [Mintlify CLI](https://www.npmjs.com/package/mint):

```bash
npm i -g mint
```

Run from the repo root (where `docs.json` lives):

```bash
mint dev
```

Preview at `http://localhost:3000`. Check for broken links with `mint broken-links`.

## Branding

The HackUTD look is defined in `docs.json` (brand colors, light/dark logos, light mode default) and `style.css` (the brand gradient background, the [Satoshi](https://www.fontshare.com/fonts/satoshi) font via Fontshare, and button styles). The site defaults to light mode.

## Deployment

Pushing to `main` triggers Mintlify's auto-deploy (via the Mintlify GitHub app) to the `*.mintlify.dev` deployment. The site is exposed at `docs.hackutd.co/docs` through `cloudflare-worker.js`, which reverse-proxies requests under `/docs` to the Mintlify origin. Update `DOCS_URL` / `CUSTOM_URL` in that file if the deployment subdomain or custom domain changes.

## Contributing

Pages are MDX files with YAML frontmatter. Configuration lives in `docs.json`. See `AGENTS.md` for style preferences (active voice, sentence-case headings, concise sentences).

## Resources

- [Mintlify documentation](https://mintlify.com/docs)
- [HackUTD](https://hackutd.co)
