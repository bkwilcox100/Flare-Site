# Flare — product website

The marketing/product site for Flare. It's a **static site** (plain HTML + CSS,
no build step). This is its own standalone repository, completely separate from
the Flare mobile app.

## Pages

| File | Route | Purpose |
|------|-------|---------|
| `index.html` | `/` | Home / product page |
| `about.html` | `/about.html` | About / mission |
| `privacy.html` | `/privacy.html` | Privacy Policy |
| `terms.html` | `/terms.html` | Terms of Service |

Shared styles live in `css/styles.css`; the design mirrors the app's "Indigo"
design tokens (accent `#4C5BD4`, Manrope, light gradient surfaces). Assets
(logo, favicon) are in `assets/`.

## Local preview

No tooling required — open `index.html` in a browser, or serve the repo root:

```bash
python3 -m http.server 8080
# then visit http://localhost:8080
```

## Deploying to GitHub Pages

Deployment is automated via GitHub Actions
(`.github/workflows/deploy-website.yml`), which publishes the whole repository to
Pages on every push to `main`.

One-time setup after pushing this repo to GitHub:

1. Go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **GitHub Actions**.
3. Push to `main` (or run the workflow manually via **Actions → Deploy website →
   Run workflow**). The site URL appears in the workflow run and on the Pages
   settings page.

### Custom domain (optional)

Add a `CNAME` file to the repo root containing your domain (e.g. `getflare.app`),
then configure the domain under **Settings → Pages**.
