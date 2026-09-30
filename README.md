# Homepage

All of the content lives in **`_data/profile.yml`**. Edit that file, commit and
push, and GitHub Pages rebuilds the site in about a minute. `index.html` is only
the template (layout, styles, light/dark switch), so you shouldn't need to touch it.

## Files

| File | What it is |
| --- | --- |
| `_data/profile.yml` | Your name, summary, links, interests, research, papers, teaching, industry |
| `index.html` | Page template, filled in from `profile.yml` when GitHub builds the site |
| `_config.yml` | Jekyll settings (leave as is) |
| `photo.jpg` | Your portrait. Add it yourself; square works best |
| `cv.pdf` | Your CV. Add it yourself |
| `papers/`, `slides/` | Optional folders for the PDFs linked from Publications |

## First-time setup

1. Create a GitHub repository named `<your-username>.github.io`.
2. Upload everything in this folder, keeping the `_data` folder as it is.
3. Add `photo.jpg` and `cv.pdf`.
4. In the repository, open **Settings → Pages** and make sure the source is the
   `main` branch, root folder. The site appears at `https://<your-username>.github.io`.

## Editing tips

- Keep text values inside `"double quotes"`.
- Fields marked *(Markdown)* in `profile.yml` accept `**bold**`, `*italic*` and
  `[link text](https://…)`.
- If you empty a list (`teaching: []`), that section and its menu link disappear.
- You can edit `profile.yml` right on github.com. Open the file, click the pencil
  icon, then **Commit changes**.
- If the site stops updating, open the repository's **Actions** tab. A failed
  build almost always means a missing quote or a wrong indent in `profile.yml`,
  and the error message gives the line number.

## Previewing on your own computer (optional)

Opening `index.html` directly shows raw `{{ … }}` tags, because the page is only
filled in when Jekyll builds it. To preview before pushing, install Jekyll and
run it in this folder:

```
gem install jekyll webrick
jekyll serve
```

Then open http://localhost:4000.
