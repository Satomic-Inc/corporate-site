# corporate-site

The public Satomic corporate / marketing website. It is a small set of static
HTML pages (no build step, no framework) served via GitHub Pages at the custom
domain in [`CNAME`](CNAME): **[satomic.ai](https://satomic.ai)**.

## Pages

| File | Purpose |
| --- | --- |
| `index.html` | Landing / "Coming Soon" page with contact links and an email-subscribe form (posts to Formspree, then redirects to `thank-you.html`). |
| `careers.html` | Careers page; links out to the Rippling job board. |
| `thank-you.html` | Confirmation page shown after a successful newsletter subscription. |

## Assets

| File | Purpose |
| --- | --- |
| `Favicon.png`, `Favicon (1).png` | Site favicons (referenced by the pages). |
| `Satomic Only (White on Black, Benzene).png` | Logo artwork. |

## Local preview

Everything is plain static HTML, so you can open a page directly in a browser:

```sh
open index.html
```

To exercise root-absolute paths (e.g. `/Favicon (1).png`, `/careers.html`) the
way they resolve in production, serve the directory over HTTP instead:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000/
```

## Deploy

The site is served by **GitHub Pages** in legacy (branch) mode: Pages builds
from the `main` branch at the repository root (`/`), so merging to `main`
publishes the site. The custom domain `satomic.ai` is set via `CNAME` with
HTTPS enforced. There is no GitHub Actions workflow in this repo — publishing
is handled by the repository's **Settings → Pages** configuration.

## Contributing

PRs require review from the corporate team (see
[`.github/CODEOWNERS`](.github/CODEOWNERS)).

## License

[MIT](LICENSE)
