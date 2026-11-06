---
name: lab-webpage
description: Edit the Önfelt Lab GitHub Pages site in this repository. Use when changing lab webpage copy, pictures, video, CSS, navigation, or when asked which file is the home, our lab, publications, immunology, or technology page. Read this before editing so you do not re-crawl onfeltlab.com.
---

# Önfelt Lab webpage

This repository is the public site. Do not re-crawl https://onfeltlab.com to find a file. Use the page map and [assets.md](assets.md).

**Live site:** https://hanqing-zhang-kth.github.io/Lab-webpage/

GitHub Pages serves the **main** branch, folder **/** (repository root). There is no custom domain.

## Rules that keep the site working

- Links, image paths, CSS, and JS must stay **relative** (`../onewebmedia/photo.jpg`, `onewebstatic/site.css`). A root-relative path (`/onewebmedia/...`, `/css/...`) is requested from `https://hanqing-zhang-kth.github.io/` and breaks under `/Lab-webpage/`.
- From `index.html`, assets are `onewebmedia/...` and `onewebstatic/...`. From `ourlab/`, `publications/`, `immunology/`, and `technology/` they are `../onewebmedia/...`. From a nested page (`immunology/NK/`, `technology/microwellchips/`, and the other subpages) they are `../../onewebmedia/...`.
- Link to a section with its directory (`ourlab/`, `immunology/NK/`), matching the existing menu. Each section is `index.html` inside that directory.
- Keep `.nojekyll` at the repository root. Do not add a `CNAME` file.
- Do not point stylesheets back at `google-fonts.php` or at `fonts.googleapis.com`. Montserrat is the local file `onewebstatic/google-fonts.css` plus the `.woff2` files in `onewebstatic/`.
- Do not hotlink `impro.usercontent.one`. Pictures live in `onewebmedia/`.
- Leave outbound links outbound (journal articles, KTH, KI, SciLifeLab, Twitter, `mailto:`).
- Some theme URLs inside shared CSS 404 on the original host too. Do not invent those files. They are listed in [assets.md](assets.md).

## Page map

| Section | HTML file | Pages URL |
| --- | --- | --- |
| Home | `index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/ |
| Our lab | `ourlab/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/ourlab/ |
| Publications | `publications/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/publications/ |
| Immunology research | `immunology/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/immunology/ |
| NK cell dynamics | `immunology/NK/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/immunology/NK/ |
| T cell dynamics | `immunology/T/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/immunology/T/ |
| Molecular engagers | `immunology/engagers/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/immunology/engagers/ |
| 3D tumor models | `immunology/3d-models/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/immunology/3d-models/ |
| Technology platforms | `technology/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/technology/ |
| Microwell chip platform | `technology/microwellchips/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/technology/microwellchips/ |
| Single cell analysis | `technology/singlecell/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/technology/singlecell/ |
| Single cell isolation | `technology/singlecellisolation/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/technology/singlecellisolation/ |
| Ultrasound cell handling | `technology/ultrasoundcellhandling/index.html` | https://hanqing-zhang-kth.github.io/Lab-webpage/technology/ultrasoundcellhandling/ |

`sitemap.xml` lists the same pages. The menu and footer in every HTML file repeat these links.

## Where files live

- **Page copy:** the HTML file in the page map. Text, headings, and which pictures a page shows are in that file.
- **Photographs, figures, GIFs, and the home video:** `onewebmedia/`. Which page uses which file is in [assets.md](assets.md).
- **CSS, JavaScript, footer icons, lightbox icons, and fonts:** `onewebstatic/`.
- **Shared chrome** (header, menu, footer, Montserrat) is the same set of CSS and JS on every page. Page-only layout rules are one small CSS file per page, also listed in [assets.md](assets.md).

A request to change a picture means: find that picture's path in [assets.md](assets.md), then replace, add, or delete **that path**. Do not rename it unless you also update every HTML reference and [assets.md](assets.md).

Filenames are exact, including spaces. A few names use a combining diaeresis (`o` + U+0308) rather than a precomposed `Ö`. Match the existing filename byte for byte. In HTML, spaces and `#` are percent-encoded (`%20`, `%23`); the file on disk is not percent-encoded.

## How to update

### Replace

Overwrite the file at the same path and filename. Leave the HTML path alone if the filename did not change. Replacing `onewebmedia/Front page_edited1.png` changes the home hero and nothing else.

### Add

1. Put the new image or download in `onewebmedia/` (or a stylesheet/script in `onewebstatic/`).
2. Reference it with a relative URL from the page that should show it. Count `../` from that page's directory (see Rules).
3. Add the path to the right page in [assets.md](assets.md).

### Delete

1. Remove the HTML (or CSS) reference.
2. Delete the file only when [assets.md](assets.md) shows no other page still uses it.
3. Remove the path from [assets.md](assets.md).

### Publish

Commit and push to **main**. GitHub Pages rebuilds from the root of `main`. Do not force-push. Do not commit secrets.

### Version log

After every edit, append an entry to [VERSION.md](VERSION.md). Do not rewrite or invent versions before 1.0.0.

- **1.0.0** (6 November 2026, 18:08 Europe/Stockholm) is the public mirror. Later entries sit above it in [VERSION.md](VERSION.md). The newest entry is the current version.
- A small edit (wording, one picture swap, a doc note that does not change the public pages) increments the patch number. The entry text is only `minor changes`.
- A major change (new section, removed page, layout or navigation change, many pictures at once) increments the minor number and records a short note of what changed.
- Put the newest entry first. Include the version, the date and time in Europe/Stockholm, and either the short note or the words `minor changes`.
