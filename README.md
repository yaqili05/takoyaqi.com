# takoyaqi.com

A one-file static site. Structure follows the MIT Self-Assembly Lab site (work grid → project pages, research, publications, press, about, collaborators, contact); the look follows Paul Pettigrew Architect (Arial, all lowercase, grey type, centered, image grid with hover labels).

```
index.html   the whole site — HTML, CSS, JS
resume.pdf   (add this) shown on the resume page
CNAME        tells GitHub Pages to serve at takoyaqi.com
images/      put your photos here
```

## Editing content

Open `index.html` and scroll to the `CONTENT` block in the `<script>` near the bottom. Every placeholder is there: `SITE`, `CATEGORIES`, `PROJECTS`, `RESEARCH`, `PUBLICATIONS`, `PRESS`, `ABOUT`, `COLLABORATORS`.

- **Add a real image:** drop `images/growing-islands.jpg` into the folder and add `img:"images/growing-islands.jpg"` to that project (or to a `gallery` entry, `RESEARCH` item, or `ABOUT`).
- **Thumbnail shape:** `ratio` is width ÷ height (1 = square, 0.75 = tall, 1.33 = wide). Mixing ratios gives the masonry look.
- **Colors / type:** change the `:root` variables at the top of the `<style>` block.

Pages use hash links (`takoyaqi.com/#/work/project-one`), so there's no build step or server config.

## Putting it on takoyaqi.com (GitHub Pages, free)

1. Create a GitHub repo (e.g. `takoyaqi.com`) and upload `index.html`, `CNAME`, and `images/`.
2. Repo → **Settings → Pages** → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`. Save.
3. At your domain registrar's DNS settings for takoyaqi.com, add:

   | Type  | Name | Value |
   |-------|------|-------|
   | A     | @    | 185.199.108.153 |
   | A     | @    | 185.199.109.153 |
   | A     | @    | 185.199.110.153 |
   | A     | @    | 185.199.111.153 |
   | CNAME | www  | `<your-github-username>.github.io` |

   Delete any existing A / "parking" records on `@` first.
4. Back in Settings → Pages, set Custom domain to `takoyaqi.com`. Once DNS resolves (minutes to a few hours), tick **Enforce HTTPS**.

**Alternative — Netlify:** drag the folder onto app.netlify.com/drop, then Domain settings → add `takoyaqi.com` and follow its DNS instructions (you can delete `CNAME`).
