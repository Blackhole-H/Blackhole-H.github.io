# Bang Hu — Academic Homepage

Personal academic website of **Bang Hu**, PhD student at the College of Computer Science
and Artificial Intelligence, Fudan University.

- Site: <https://blackhole-h.github.io/>
- Built with [al-folio](https://github.com/alshedivat/al-folio) v1.x + Jekyll
- Hosted on GitHub Pages

Research: **brain-inspired computing and embodied intelligence** — spiking neural networks,
efficient neural computation, and long-horizon memory for embodied agents.

## Structure

```
_pages/about.md          Homepage (hero, research interests, selected publications, current research)
_pages/publications.md   Publications page (generated from the bibliography by Jekyll Scholar)
_pages/research.md       Research page (two research areas)
_bibliography/papers.bib All publications — add a paper here and it appears everywhere
_data/socials.yml        Email / GitHub / ORCID / Scholar / CV links
_data/venues.yml         Venue abbreviations used by the `abbr` bib field
_includes/site-extras.html  Shared CSS for the research-interest cards
assets/img/              Profile photo, favicons, OG image, publication previews
```

## Everyday maintenance

See [`MAINTENANCE.md`](MAINTENANCE.md) (in Chinese) — how to update your bio, add a paper,
swap a thumbnail, update research interests, add a CV, preview locally, and publish.

Missing content that is deliberately hidden rather than faked is listed in
[`CONTENT_TODO.md`](CONTENT_TODO.md).

## Local preview

```bash
bundle install
bundle exec jekyll serve     # http://localhost:4000/
```

`baseurl` must stay empty — this is a `username.github.io` site.

## Deployment

Pushing to `main` triggers `.github/workflows/deploy.yml`, which builds the site and
publishes it to the `gh-pages` branch. One-time repository setup:

1. Settings → Actions → General → Workflow permissions → **Read and write permissions**
2. Settings → Pages → Build and deployment → **Deploy from a branch** → branch **gh-pages**
