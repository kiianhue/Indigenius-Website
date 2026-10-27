# Indigenius

A platform supporting Indigenous students pursuing careers in healthcare. Senior capstone project, Department of Biology, Stanford University.

## Sections

- **Exploring Healthcare** — twenty health professions with education paths, length, and BLS median wages
- **Stories & Voices** — podcast conversations with Indigenous healthcare leaders
- **Opportunities & Support** — scholarships, pathway programs, and organizations

## Structure

```
public/                      everything served to visitors
  index.html
  exploring-healthcare.html
  stories-and-voices.html
  opportunities.html
  404.html
  styles.css                 shared styles for all pages
wrangler.jsonc               Cloudflare Workers config
```

Plain HTML and CSS. No build step, no framework, no dependencies.

## Local preview

Open `public/index.html` in a browser, or serve the folder:

```bash
npx wrangler dev
```

## Deploy

Cloudflare Workers Builds deploys automatically on every push to `main`.

Manual deploy:

```bash
npx wrangler deploy
```

## Adding a podcast episode

Episode videos are not stored in this repo — the `.mp4` files are far too large for Git. Upload each episode to YouTube or Vimeo, then in `stories-and-voices.html` replace that episode's `<div class="embed-slot">…</div>` with:

```html
<div class="embed-slot">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID"
          title="Episode title"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; picture-in-picture"
          allowfullscreen></iframe>
</div>
```

## Updating content

Wage figures come from the U.S. Bureau of Labor Statistics [Occupational Outlook Handbook](https://www.bls.gov/ooh/healthcare/) (May 2025) and should be refreshed each year. Scholarship deadlines change annually — verify them against each program's own site before each application cycle.
