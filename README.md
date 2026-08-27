> [!NOTE]
> AI GENERATED

 
# devanksingh.github.io — Minimal GitHub Pages site

This repository contains a minimal static site scaffold for GitHub Pages.

- Site source: `public/` — see [public/index.html](public/index.html)
- Styles: [public/assets/style.css](public/assets/style.css)
- GitHub Actions workflow: [.github/workflows/gh-pages.yml](.github/workflows/gh-pages.yml)

How to use

1. Rename the repository to `devanksinghchaudhary.github.io` if you want a user site directly served at `https://devanksinghchaudhary.github.io`.
2. Push the repository to GitHub (e.g., `git remote add origin ...` and `git push -u origin main`).
3. The workflow will publish the contents of `public/` to the `gh-pages` branch automatically on push to `main`/`master`.

If you prefer GitHub Pages to serve from the `main` branch (root or `/docs`), adjust the workflow or GitHub repository settings accordingly.

Repository settings note:

- Ensure Actions have **Read and write permissions**: Settings → Actions → General → *Workflow permissions* → select **Read and write permissions**, and enable **Allow GitHub Actions to create and approve pull requests** if applicable. This lets the `GITHUB_TOKEN` push the `gh-pages` branch.


