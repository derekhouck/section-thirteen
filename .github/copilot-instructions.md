# Section Thirteen (sectionthirteen.com)

A Jekyll static site for a motion picture production company, migrated from
WordPress (see `README.md`). Content is mostly static marketing/press pages
plus a WordPress-exported post archive.

## Build & Development Commands

- Install dependencies: `bundle install`
- Run local dev server (live at `http://localhost:4000`): `bundle exec jekyll serve`
- Build static site to `_site/`: `bundle exec jekyll build`
- **Changes to `_config.yml` require restarting the dev server** — it is not
  reloaded automatically by `jekyll serve`.
- There are no automated tests or linters configured in this repo.

## Architecture

- **Jekyll + `minima` theme** (see `Gemfile`/`Gemfile.lock`). Only the
  `jekyll-feed` plugin is enabled (`_config.yml`).
- **Layout inheritance chain**: `default.html` (site chrome: `head`, `header`,
  `footer` includes) → `post.html` / `page.html` / `home.html` /
  `category.html`, each of which sets `layout: default` in its own front
  matter and is rendered via `{{ content }}`.
  - `post.html`: single blog post article (schema.org `BlogPosting` markup),
    optional Disqus comments via `disqus_comments.html`.
  - `category.html`: renders a page's own content plus every post whose
    `categories` includes `page.category` (used by `press_releases.md`).
  - `home.html`: lists every post in `site.posts`.
- **Top navigation** is driven by `header_pages` in `_config.yml`, not by
  directory structure — currently `superfan.md` and `press_releases.md`.
  Add new top-level nav pages there.
- `_posts/` contains WordPress-exported posts. Front matter retains legacy
  WordPress fields (`id`, `guid`, `permalink`, `categories`) alongside
  standard Jekyll fields (`title`, `date`, `author`, `layout: post`). Keep
  this shape when adding/editing posts so category archive pages and
  permalinks keep working.
- `superfan/` holds content pages specific to the "Superfan" short film
  (cast, trailer, full film), separate from the press-release post archive.
- `assets/img/` stores images referenced by pages/posts (paths like
  `/assets/img/2014/05/...`).
