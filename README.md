# Lab-webpage

Mirror of the Önfelt Lab website ([onfeltlab.com](https://onfeltlab.com)), published with GitHub Pages.

**Pages:** https://hanqing-zhang-kth.github.io/Lab-webpage/

## Update content

Replace the asset or HTML file in place (same path and filename), commit, and push to `main`. GitHub Pages serves this repository from the root of `main` and rebuilds after the push.

- Home page: `index.html`
- Section pages: `ourlab/index.html`, `publications/index.html`, `immunology/index.html`, `technology/index.html`, plus the nested pages under `immunology/` and `technology/`
- Images and video: `onewebmedia/`
- Styles, scripts, and fonts: `onewebstatic/`

Keep links relative so they keep working under the `/Lab-webpage/` base path. The `.nojekyll` file stops GitHub Pages from running Jekyll on the mirror.

Agents editing this site should read `AGENTS.md`, then follow `docs/lab-webpage-agent.md`. The version log is `docs/VERSION.md`.

## Differences from onfeltlab.com

- The site is served at https://hanqing-zhang-kth.github.io/Lab-webpage/, not at the domain root, so root-relative URLs would miss `/Lab-webpage/`.
- Links, images, CSS, and JS are relative so they resolve under that base path.
- `.nojekyll` is in the repo root so GitHub Pages does not run Jekyll on the mirrored HTML.
- Montserrat is stored as `onewebstatic/google-fonts.css` and local `.woff2` files. GitHub Pages cannot run the original `google-fonts.php` script.
- Images and video were copied from `onfeltlab.com/onewebmedia/`. The One.com image CDN (`impro.usercontent.one`) is not used.
- Links to journals, KTH, KI, SciLifeLab, Twitter, and email stay outbound. They are not copied into the repo.
- Shared theme CSS still names a few files the original host itself returns 404 for (`img/down.svg`, `img/up.svg`, and unused template PNGs under `api/v1/repository/webspace/`). Those files were not invented.
- No custom domain is configured. The address stays on `github.io`.
