# LuminOS Docs + Community

Mintlify documentation for the **LuminOS** Shopify theme, plus wiring for a Discourse community.

| Surface | URL |
| --- | --- |
| Docs | https://docs.lumintheme.com |
| Community | https://community.lumintheme.com |
| Marketing site | https://lumintheme.com |

Theme source used for generated section pages: sibling folder `../LuminOS New` (override with `LUMINOS_THEME_PATH`).

## Local development

```bash
# Optional: install Mintlify CLI
npm i -g mintlify

# Regenerate section/block reference from the theme
npm run generate

# Preview docs
npm run dev
```

## Generate section reference

`scripts/generate-docs.mjs` reads Liquid `{% schema %}` blocks from the theme and writes `sections/*.mdx`. Content inside `<!-- MANUAL:START -->` … `<!-- MANUAL:END -->` is preserved across runs. The **Sections** group in `docs.json` is updated automatically.

```bash
LUMINOS_THEME_PATH="/path/to/LuminOS New" npm run generate
```

## Launch guides (hand-written)

See `introduction.mdx`, `getting-started/`, `guides/`, `troubleshooting/`, and `changelog.mdx`. Loom/YouTube embeds use a `VIDEO_ID` placeholder until you record videos.

## DNS checklist

1. Create a Mintlify project and connect this repo.
2. Add custom domain **docs.lumintheme.com** in Mintlify; create the DNS records Mintlify shows (usually CNAME).
3. Create a Discourse hosted site; add custom domain **community.lumintheme.com** and apply Discourse DNS records.
4. On **lumintheme.com**, add header links: **Docs** → `https://docs.lumintheme.com`, **Community** → `https://community.lumintheme.com`.
5. Confirm theme info URLs in LuminOS `config/settings_schema.json`:
   - `theme_documentation_url` → `https://docs.lumintheme.com`
   - `theme_support_url` → `https://community.lumintheme.com`

## Discourse checklist

1. Categories (slug examples used in doc links):
   - **Announcements** (staff only) — `announcements`
   - **Setup help** — `setup-help`
   - **Customization** — `customization`
   - **Bugs** — `bugs`
   - **Feature requests** — `feature-requests`
2. Public read; require login to post.
3. Point category URLs so links like `https://community.lumintheme.com/c/setup-help` resolve (adjust slugs in MDX if Discourse uses different permalinks).
4. Link back to docs from the Discourse header.

## Access / gating

v1 is public docs + public read forum. License gating is deferred.

## License

Documentation © Lumintheme. Theme files remain under your theme license.
