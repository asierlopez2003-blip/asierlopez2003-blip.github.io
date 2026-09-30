# asierlopez2003-blip.github.io

Personal professional website for **Asier López Mantecón** — physicist working on
particle physics, astroparticles, and their computational and biomedical applications.

Live site: <https://asierlopez2003-blip.github.io>

## Stack

[Jekyll](https://jekyllrb.com) with the [Academic Pages](https://github.com/academicpages/academicpages.github.io)
theme, deployed by GitHub Pages. The `github-pages` gem is pinned in `Gemfile`, so themes
and plugins resolve on GitHub's build servers — no local Ruby build is required or
supported.

## Where things live

| Path | Contents |
|---|---|
| `_config.yml` | Site-wide settings, theme, defaults |
| `_pages/` | Top-level pages (`about.md`, `cv.md`, `expediente.html`, 404, …) |
| `_data/` | YAML data: `titulos.yml`, `experiencia.yml`, `habilidades.yml`, `congressos.yml`, `navigation.yml` |
| `_publications/`, `_talks/`, `_portfolio/`, `_teaching/` | Jekyll collections, one file per entry |
| `_posts/` | Blog |
| `_sass/` | Styles. Theme styles are not modified; custom rules are namespaced |
| `_includes/`, `_layouts/` | **Do not edit.** Upstream template internals |
| `files/` | PDFs and other downloads, served at `/files/…` |
| `images/` | Images; the sidebar avatar is `profile.png` |

## Content model

The site is the *unfiltered* professional record. Anything too specific for a CV
belongs here. Degrees, certifications, and awards are grouped in `_data/titulos.yml`
and rendered by `_pages/expediente.html` with native `<details>` elements — no
JavaScript, no proficiency levels.

`/cv/` is the single CV surface, condensed from the same `_data`. There is no
separate structured-JSON CV page: the template's demo page and its generator
were removed rather than shipped with placeholder content.

## Credits

Built on the [Academic Pages](https://github.com/academicpages/academicpages.github.io)
template (MIT), itself a fork of [Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes)
by Michael Mañana. The template's upstream history is not tracked here; see the project
notes for the exact commit this was forked from.

Licensed [MIT](LICENSE).
