# Olinfo

A Quarto website for an in-person lecture series in competitive programming and computer science olympiad topics.

## Preview locally

Install [Quarto](https://quarto.org/docs/get-started/) and run:

```sh
quarto preview
```

The website configuration lives in `_quarto.yml`. Add a lecture by creating a `.qmd` file under `lectures/` and adding it to both the overview page and sidebar.

## Publish to GitHub Pages

In the repository's **Settings → Pages**, set **Source** to **GitHub Actions**.
Then commit and push the publishing workflow to `main`.

Every push to `main` runs [the publishing workflow](.github/workflows/publish.yml),
which renders the site with Quarto, commits the contents of `_site/` to the root
of the `gh-pages` branch, and deploys the rendered site to GitHub Pages. The
`gh-pages` branch is created automatically and contains only generated files;
`main` keeps the source files. If the rendered output is unchanged, no new
`gh-pages` commit is created.

The workflow deploys directly because commits made with `GITHUB_TOKEN` do not
trigger branch-based GitHub Pages builds. It uses the built-in token, so no
personal access token is needed. You can also run it manually from
**Actions → Publish website → Run workflow**, selecting `main`.

The published site will be available at
<https://alvisesembenico.github.io/olinfo-workshop/>.
