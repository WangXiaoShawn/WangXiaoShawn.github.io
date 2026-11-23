# Xiao Wang — academic homepage

Static site served by GitHub Pages at <https://wangxiaoshawn.github.io/>. No build step.

## Layout

```
index.html                    Homepage (jemdoc-style layout)

projects/                     One folder per publication / project on the homepage
  <name>/
    index.html                  project page, served at /projects/<name>/
                                (only for projects hosted on this site)
    files/                      paper / slides / poster PDFs (e.g. mistypilot, automisty)
    img/
      teaser.png                  top figure on the project page
      thumbnail.(png|gif|jpg)     homepage thumbnail (omitted when teaser.png is reused)

  With a local page:  mistypilot, automisty, interventionlens, evomisty (under review),
                      misty-therapy
  Thumbnail only (page hosted elsewhere or none):
                      confusionbench, ig3d, wsigngen, proxyfusion, signavatar,
                      arl-intersect, theorem-proving, xiaostyle-ecommerce,
                      data-navigator, factory-multithreading, remote-process-control,
                      network-security, recruitpro

assets/                       Shared site assets
  css/  js/                   Homepage stylesheet and jQuery
  img/wangxiao.png            Profile photo
  img/icons/                  Social / CV link icons
  img/gifs/                   Decorative gifs on the homepage

resume/                       My CV (Phd_Resume_XiaoWang.pdf) — replace the file in place to update

404.html                      Not-found page that also forwards old URLs (MistyPilot.html
                              on the ECCV 2026 poster QR code, old files/*.pdf links)
                              to their new locations. Do not delete.

docs/                         Design notes
_drafts/                      Local-only working files (git-ignored, never published)
```

## Conventions

- **New publication / project** → create `projects/<lowercase-name>/img/thumbnail.*`;
  add `index.html` there if it gets a page on this site.
  Copy an existing project page as the template. From inside a project page, shared
  paths are `../../index.html`, `../../assets/…`, `../../resume/…`.
- **PDFs** of a project (paper, slides, poster) go in `projects/<name>/files/`. If one
  moves, add it to `MOVED` in `404.html`.
- **CV** lives at `resume/Phd_Resume_XiaoWang.pdf`. To update it, overwrite that file
  with the same name so external links (LinkedIn, applications) keep working.
- **Moving a page or PDF** → add `old path -> new path` to the `MOVED` table in
  `404.html`, so links already shared keep working.
- **Image names** are lowercase-kebab-case.
- Project pages use the NeRFies/Bulma template and load Bulma and Font Awesome from
  CDNs. Only the homepage uses the local CSS/JS in `assets/`.
- Drafts, social-media posts and other non-site files go in `_drafts/`.
