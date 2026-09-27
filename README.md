# StackPilot — autonomous blog (AI tools & SaaS for solopreneurs)

Static site (plain HTML, no build step) published for free on GitHub Pages. A scheduled Claude Code agent writes and publishes a new article automatically, without using any paid API.

## How it works
- `topics.json` stores the niche and the list of pending/used topics.
- `AGENT_INSTRUCTIONS.md` is what the scheduled session follows on every run.
- Each run adds a post under `posts/`, updates `index.html` and `sitemap.xml`, and pushes to GitHub.

## What's left for you to do (I can't create accounts for you)
1. **Enable GitHub Pages**: in the repo, go to *Settings → Pages → Source: Deploy from a branch → main / (root)*. The site goes live at `https://yunkwani.github.io/pagina1/` within a few minutes.
2. **Ad monetization (optional, once you have traffic)**: create a free [Google AdSense](https://adsense.google.com) account, request site approval, and add your ad script to `assets/` or directly in each page's `<head>`.
3. **Affiliate monetization (optional)**: join an affiliate program relevant to AI tools/SaaS (e.g. individual tool affiliate programs, or a network like PartnerStack/Impact) and replace generic product mentions in articles with your real affiliate links.

## Cost
$0. No API keys, no paid hosting, no custom domain (uses the free GitHub Pages subdomain).
