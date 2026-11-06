# Edit the Önfelt Lab website

This repository is the public site at https://hanqing-zhang-kth.github.io/Lab-webpage/. Do not crawl https://onfeltlab.com to find a file. Use the page map below and [assets.md](assets.md).

GitHub Pages serves the `main` branch, folder `/` (the repository root). There is no custom domain.

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

- Page text is in the HTML file from the page map.
- Photographs, figures, GIFs, and the home video are in `onewebmedia/`. The path for each one is in [assets.md](assets.md).
- CSS, JavaScript, icons, and fonts are in `onewebstatic/`. Shared files and the one page-specific CSS file per page are also in [assets.md](assets.md).

## Rules

1. Keep links relative. From `index.html` use `onewebmedia/photo.jpg` and `onewebstatic/site.css`. From `ourlab/`, `publications/`, `immunology/`, and `technology/` use `../onewebmedia/photo.jpg`. From a nested page such as `immunology/NK/` or `technology/microwellchips/` use `../../onewebmedia/photo.jpg`.
2. Do not use a root-relative path such as `/onewebmedia/photo.jpg` or `/css/site.css`. The browser would request it from `https://hanqing-zhang-kth.github.io/` and skip `/Lab-webpage/`.
3. Link to a section with its directory (`ourlab/`, `immunology/NK/`). Each section is `index.html` in that directory.
4. Leave `.nojekyll` at the repository root. Do not add a `CNAME` file.
5. Do not point stylesheets at `google-fonts.php` or `fonts.googleapis.com`. Montserrat is `onewebstatic/google-fonts.css` and the `.woff2` files in `onewebstatic/`.
6. Do not hotlink `impro.usercontent.one`. Pictures live in `onewebmedia/`.
7. Leave journal, KTH, KI, SciLifeLab, Twitter, and `mailto:` links as outbound URLs.
8. Do not create the theme files that [assets.md](assets.md) lists as 404s on the original host.
9. Filenames are exact, including spaces. A few names use `o` plus a combining diaeresis (U+0308) instead of a precomposed `Ö`. Match the existing filename byte for byte. In HTML, spaces and `#` are percent-encoded (`%20`, `%23`). The file on disk is not percent-encoded.

## Change a picture or video

1. Open [assets.md](assets.md) and find the page.
2. To replace: overwrite that exact path and filename. Do not change the HTML path if the filename stays the same. Example: overwriting `onewebmedia/Front page_edited1.png` changes the home hero only.
3. To add: save the new file under `onewebmedia/` (or `onewebstatic/` for a stylesheet or script). In the page HTML, add a relative URL. Count `../` using the Rules above. Add the path under that page in [assets.md](assets.md).
4. To delete: remove the reference from the HTML. Delete the file only if [assets.md](assets.md) shows no other page uses it. Remove the path from [assets.md](assets.md).
5. Do not rename a file unless you update every HTML reference and [assets.md](assets.md).

## Publish

1. Append a version entry to [VERSION.md](VERSION.md). Put the newest entry first. Do not edit the 1.0.0 entry or invent versions before it.
2. For a small edit, increment the patch number. The entry text is only `minor changes`.
3. For a major change (new section, removed page, layout or navigation change, many pictures at once), increment the minor number and write a short note of what changed.
4. Each entry has the version, the date and time in Europe/Stockholm, and either the short note or the words `minor changes`.
5. Commit and push to `main`. GitHub Pages rebuilds from the root of `main`. Do not force-push. Do not commit secrets.
