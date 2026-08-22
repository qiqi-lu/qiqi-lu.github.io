# Qiqi Lu — Academic Homepage

Personal academic homepage built with [Jekyll](https://jekyllrb.com/), based on the [Lagrange](https://github.com/LeNPaul/Lagrange) theme. Deployed on GitHub Pages at <https://qiqi-lu.github.io>.

## Run locally

```bash
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>.

## Structure

```
_data/            Site data (publications.yml, awards.yml, news.yml, settings.yml)
menu/             Page content (About, Publications, Patents, Awards, News, Contact)
_includes/        Layout partials (head, header, menu, footer, social icons)
_layouts/         Page templates (default, page)
assets/           Compiled CSS and images
```

## Update content

- **Publications** — edit `_data/publications.yml` (newest first).
- **Awards** — edit `_data/awards.yml` (newest first; `date` is the display date).
- **News** — edit `_data/news.yml` (newest first; `date` is the display date).
- **Menu / social links** — edit `_data/settings.yml`.
