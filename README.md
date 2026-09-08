# Xiao Wang — academic homepage

Static site served by GitHub Pages at <https://wangxiaoshawn.github.io/>. No build step.

## Layout

```
index.html              Homepage (jemdoc-style layout)
MistyPilot.html         Project page — MistyPilot (ACVR @ ECCV 2026)
AutoMisty.html          Project page — AutoMisty (IROS 2025)
InterventionLens.html   Project page — InterventionLens (CV4Edu @ CVPR 2026)
misty.html              Legacy project page (not linked from the homepage)

assets/                 Site assets
  css/                  jemdoc.css (homepage stylesheet)
  js/                   jquery-1.12.4.min.js (homepage)
  img/                  wangxiao.png (profile photo)
    icons/              Social / CV link icons
    gifs/               Decorative gifs used on the homepage
    pubs/               Publication thumbnails and project figures

files/                  Downloadable PDFs (papers, slides, posters, CV)

docs/                   Design notes
sitemap.xml             Sitemap for this domain
```

## Conventions

- Keep the root HTML files and everything under `files/` at their current paths.
  Those URLs are printed on posters (QR codes), cited in papers, and shared
  externally; renaming them breaks inbound links.
- Project pages use the NeRFies/Bulma template and load Bulma, Font Awesome and
  jQuery from CDNs. Only the homepage uses local CSS/JS.
- Put new figures in `assets/img/pubs/`, new PDFs in `files/`.
