# DocuFlow — Improved Project

DocuFlow combines your existing HTML demo with a real Markdown documentation site and GitHub automation.

## Project parts

- `index.html` — your existing interactive DocuFlow prototype.
- `docs/` — Markdown documentation used by MkDocs.
- `mkdocs.yml` — MkDocs Material website configuration.
- `.github/workflows/ci-cd.yml` — validates Markdown, checks links, builds the site, and deploys to GitHub Pages.
- `.markdownlint.json` — Markdown formatting rules.
- `.lychee.toml` — link checker settings.

## Run locally

1. Install Python 3.10 or newer.
2. Open this folder in VS Code.
3. Open the VS Code terminal (Terminal → New Terminal).
4. Run:

```bash
python -m pip install -r requirements.txt
mkdocs serve
```

5. Open the local address printed in the terminal (usually http://127.0.0.1:8000).

Your HTML prototype can be opened separately by double-clicking `index.html`.

## Publish on GitHub

Create a GitHub repository named `DocuFlow`, then run these commands in this folder:

```bash
git init
git add .
git commit -m "Add improved DocuFlow project"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/DocuFlow.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username.

Then open the repository's **Settings → Pages** and set **Build and deployment → Source** to **GitHub Actions**.

After a push to `main`, GitHub Actions checks the Markdown and links, builds the MkDocs site, and deploys it to GitHub Pages.

## Important note about the Publish button

The existing HTML demo is preserved as a browser-only prototype. A static HTML page cannot securely create GitHub branches or pull requests without a secure backend or GitHub App. Do not put a GitHub personal access token in browser JavaScript.
