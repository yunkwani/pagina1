# Instructions for automatic publishing

This file is read by the scheduled Claude Code session on every run. No API key is needed: Claude Code itself (using the user's existing subscription) writes the article, not a paid external script.

On every run:

1. Read `topics.json`. Take the first topic from `upcoming_topics`.
2. Write a new article at `posts/<topic-slug>.html`, following the exact structure and style of `posts/ai-tools-that-actually-save-freelancers-time.html` (same `<head>` INCLUDING the AdSense `<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-8900400906289730" crossorigin="anonymous"></script>` tag, same `assets/style.css`, affiliate disclosure at the end, 500-800 words, practical no-hype tone, `lang="en"`). Stick to the niche defined in `topics.json`. Never present fabricated hands-on testing or benchmark numbers as real — write from general knowledge and clearly framed comparisons, not invented first-hand claims.
3. Move that topic from `upcoming_topics` to `used_topics` in `topics.json`. If `upcoming_topics` is empty, generate 10 new topics within the same niche (`niche` in `topics.json`) and add them.
4. Insert a new `<div class="post-list-item">` entry in `index.html`, right before the `<!-- NEW_POSTS -->` comment, linking to the new post.
5. Add the new post's URL to `sitemap.xml`.
6. Run:
   ```
   git add -A
   git commit -m "New post: <title>"
   git push origin main
   ```
7. Do not ask for confirmation for these steps: this task is pre-authorized to run autonomously. If `git push` fails (e.g. credentials), report it but do not retry in a loop.

Do not add Node/npm dependencies or a build step: the site must stay plain HTML served directly by GitHub Pages.
