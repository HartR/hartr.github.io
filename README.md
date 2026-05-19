# Hart's Notebook

A small custom Jekyll site for GitHub Pages with a homepage, one blog post, and resume links.

## Local development

Install Ruby and Bundler, then run:

```bash
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`.

## Publishing

Push changes to the `main` branch of `HartR/hartr.github.io`. GitHub Pages will build and publish the site automatically.

## Editing

- Blog posts live in `_posts/` and use the filename format `YYYY-MM-DD-title.md`.
- The homepage lives in `index.md`.
- The blog archive lives in `pages/blog.md`.
- Resume source lives in `resume.tex`; the compiled PDF is `assets/cv.pdf`.
- Global styles live in `assets/css/style.css`.
