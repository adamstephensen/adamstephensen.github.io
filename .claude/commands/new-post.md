---
description: Scaffold a new blog post with the right path, filename and front matter
argument-hint: <post title>
allowed-tools: Bash, Read, Write, Edit, Glob, Grep
---

Create a new draft post titled: **$ARGUMENTS**

Follow `.claude/skills/blog-post/SKILL.md` exactly. Steps:

1. Get today's date with `date +%Y-%m-%d`. Do not guess it.
2. Derive a lowercase dash-separated slug from the title.
3. Create `_posts/YYYY-MM/` if needed, then write
   `_posts/YYYY-MM/_YYYY-MM-DD-Title-With-Dashes.md` — note the **leading underscore**, so it
   stays unpublished until it's ready.
4. Front matter: quoted `title`, `permalink: /YYYY/MM/DD/slug/`, `layout: post`, and `tags`
   picked from the tags already in use (run the tag frequency command in the skill first).
   If you can't confidently pick tags from the title, leave the list with a single
   `# TODO` comment rather than inventing one.
5. Leave the body as a one-line placeholder unless the user gave you material to write from.
6. Report the file path, the permalink it will publish at, and remind them the leading `_`
   must be removed to publish.

Do not commit or push.
