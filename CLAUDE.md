# adamstephensen.com

Personal blog. Jekyll + the `github-pages` gem, served by **GitHub Pages classic build**
(no Actions workflow) from `main`. Custom domain via `CNAME` → adamstephensen.com.
Pushing to `main` publishes. There is no staging site.

## Layout

| Path | What it is |
|---|---|
| `_posts/YYYY-MM/` | Posts, grouped in month folders (Jekyll still reads them) |
| `assets/images/YYYY-MM/` | Post images, one folder per month, matching the post |
| `assets/content/` | Downloadable handouts, slides, PDFs |
| `_includes/`, `_layouts/` | Overrides on top of the `minima` theme |
| `assets/main.scss` | **All site styling.** The dark-blue editorial theme lives here |
| `_plugins/` | Custom Ruby plugins - see caveat below |
| `_site/` | Build output. Never edit, never commit (gitignored) |

## Writing a post

Read `.claude/skills/blog-post/SKILL.md` before writing or editing a post - it has the
front matter, filename, tag and image conventions. `_posts/_template.md` is the starting point.

Short version: `_posts/YYYY-MM/YYYY-MM-DD-Title-With-Dashes.md`, front matter with
`title` / `permalink` / `layout: post` / `tags`, images at `/assets/images/YYYY-MM/`.

## Styling

The theme is `minima`, heavily overridden. Everything visual is in `assets/main.scss`;
`_includes/head.html` overrides minima's own head to pull in `assets/main.css` plus
`_includes/head-custom.html`, which loads the favicon and the Fraunces + Inter webfonts from
Google Fonts. Change styling in `assets/main.scss` - not in the theme gem, and not by adding
new stylesheets.

## Local preview

```bash
bundle exec jekyll serve --livereload
```

Serves on http://localhost:4000. `.claude/launch.json` wires this to the Browser pane, so
`preview_start` opens it directly. First time on a new machine:

```bash
bundle config set --local path vendor/bundle && bundle install
```

This works on the macOS **system Ruby (2.6)** - `Gemfile.lock` is pinned to a Ruby 2.6-compatible
set (`jekyll 3.9.5`, `nokogiri 1.13.10`). You do not need rbenv, Homebrew Ruby or a version
manager. The `gem update --system` warning bundler prints is noise; ignore it.

## Things that will bite you

- **`_plugins/` does not run on GitHub Pages.** The classic build ignores custom plugins for
  security. `_tag_gen.rb` (tag index pages) and the custom `youtube`
  Liquid tag work locally and silently do nothing in production.
  Verified: `/tag/AI/` renders locally and returns 404 on the live site. Don't add features that depend on `_plugins/`.
- **Files starting with `_` inside `_posts/` are ignored by Jekyll.** That's the de facto
  draft mechanism here (`_template.md`, `_2024-02-24-welcome-to-jekyll.markdown`). Prefix a
  post with `_` to unpublish it; there is no `_drafts/` folder.
- `Gemfile.lock` is committed and pinned. Don't run `bundle update` casually - GitHub Pages
  pins its own dependency set, and drift makes local and production disagree.
- `permalink` is what old inbound links depend on. Never change one on an existing post.
- **Anything at the repo root is published unless excluded.** `CLAUDE.md` and `.claude/` are
  listed under `exclude:` in `_config.yml`. Add new tooling files there too, or they end up
  on the live site - and a stray Liquid tag in one will break the build outright.

## Conventions

- Commit and push only when asked. Pushing to `main` is a publish.
- Prose is Australian English.
- **No em or en dashes anywhere** (U+2014 and U+2013, the long dashes) - in posts, docs
  or commit messages. Em dashes especially read as AI-generated. Use ` - `, a comma, or
  two sentences. Check with `grep -rn $'\u2014\|\u2013' _posts/`.
