# khnguyxn.eu

Khanh Nguyen's personal website — a Jekyll site with a custom, **minimalissimo-inspired** theme
(after [minimalissimo.com](https://minimalissimo.com)). It hosts an About page, a CV, and a
Writings (blog) section with full LaTeX math support.

Live at **https://www.khnguyxn.eu**.

## Design

The visual system is hand-written (with Claude) and lives almost entirely in
[`assets/css/minimalissimo.css`](assets/css/minimalissimo.css). It intentionally replaces the
original Academic Pages / Minimal Mistakes styling.

- **Typeface** — [Geist Sans](https://vercel.com/font) for body and UI (loaded from jsDelivr),
  a system monospace stack for meta labels.
- **Palette** — white canvas, near-black text, muted greys, and a single orange accent
  (`#ff4400`). No borders beyond hairlines.
- **Layout** — a wide editorial container (`max-width: 125rem`, ~2000px) with a 50/50 grid and
  a 16px gutter, matching minimalissimo's column edges. Tight vertical rhythm.
- **Header** — a breadcrumb "directory" on the top-left (`khnguyxn / Writings / …`) and the
  post date on the top-right.
- **Navigation** — a floating pill docked at the bottom-centre (back-to-top · wordmark · menu);
  the menu button opens a pop-up list (Home / Writings / CV). Pure CSS, no JS.
- **Home** — a hero with the wordmark in the left rail and a right-aligned 24px intro statement,
  followed by a horizontal author band and a grid of post cards.
- **Posts** — the layout adapts to the content:
  - posts **with an image** (a front-matter `image:` or an `<img>` in the body) use the
    two-column layout (media left, text right);
  - posts **without images** render as a centred reading column.
- **CV** — the PDF embed and download button are centred (`wide` page).
- **Math** — [MathJax 4](https://www.mathjax.org/) with the sans-serif **Fira** math font,
  sized to match the body text and rendered on the text baseline.

### Where things live

| Path | Purpose |
| --- | --- |
| `assets/css/minimalissimo.css` | The entire design system |
| `_layouts/default.html` | Page skeleton: `<head>`, breadcrumb header, footer, floating pill, pop-up menu, fonts + MathJax |
| `_layouts/home.html` | Home hero + author band + writing grid |
| `_layouts/single.html` | Posts/pages: two-column (with images) or centred (without); `wide` for the CV |
| `_layouts/archive.html` | Listings (Writings index, sitemap, taxonomies) |
| `_includes/` | `footer-mini`, `author-band`, `posts-grid`, `post-content` partials |
| `_data/navigation.yml` | Top-level nav (Writings, CV) |
| `_pages/` | `about.md` (home, `/`), `cv.md`, `year-archive.html` (Writings) |
| `_posts/` | Blog posts (Markdown, with `$$…$$` / `\(…\)` math) |

## Adding content

- **A blog post** — add `_posts/YYYY-MM-DD-title.md` with front matter `title`, `date`, and
  optional `tags`. Add `image: /images/foo.jpg` if you want the two-column layout with a
  featured image; otherwise it renders centred.
- **Files** (PDFs, slides, etc.) — drop them in `files/`; they're served at `/files/…`.
- **Navigation** — edit `_data/navigation.yml`.
- **Author details** (name, bio, socials) — edit the `author:` block in `_config.yml`.

## Running locally

You need Ruby (with `ruby-dev`), Bundler, and Node.

```bash
# macOS
brew install ruby node
gem install bundler
```

Then, from the repository root:

```bash
bundle install                       # install Ruby dependencies (delete Gemfile.lock if it errors)
bundle exec jekyll serve -l -H localhost
```

The site is served at http://localhost:4000. Markdown/HTML changes rebuild automatically;
changes to `_config.yml` require restarting Jekyll.

> Note: internal links and assets use `relative_url` (root-relative), so the local preview and
> the production build behave the same.

### Using Docker

```bash
chmod -R 777 .
docker compose up
```

The site will be available at http://localhost:4000.

## Credits

- Design inspired by **[Minimalissimo](https://minimalissimo.com)**.
- Built on **Jekyll**; the project began as a fork of
  [Academic Pages](https://github.com/academicpages/academicpages.github.io) (itself a fork of the
  [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/) theme, © Michael Rose, MIT).
- Fonts: **Geist Sans**; math set in **Fira** via **MathJax 4**.

Released under the MIT License (see [LICENSE](LICENSE)).
