# Weiyi Pan — Academic Website

Personal academic website built with **GitHub Pages + Jekyll**.

## Pages

- Home
- CV
- Research
- Publications
- Photos

## Publish on GitHub Pages

1. Log in to GitHub as **Weiyi1029**.
2. Create a new **public** repository named exactly `Weiyi1029.github.io`.
3. Upload all files and folders from this project to the repository root.
4. Commit the files to the `main` branch.
5. Open **Settings → Pages**.
6. Under **Build and deployment**, select **Deploy from a branch**.
7. Choose branch `main` and folder `/ (root)`, then click **Save**.
8. After GitHub finishes building, visit `https://weiyi1029.github.io`.

## Edit later

### Add/update a publication
Edit `_data/publications.yml`. Each item has `year`, `title`, `authors`, `venue`, and optionally `url`, `featured`, and `note`.

### Replace the home photo
Replace `assets/images/home.jpg` while keeping the same filename.

### Add photos
Put new optimized images in `assets/images/`, then add another `<figure>` block in `photos.md`.

### Replace the CV
Replace `assets/files/Weiyi_Pan_CV.pdf` while keeping the same filename.

## Local preview (optional)

If Ruby and Bundler are installed:

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://127.0.0.1:4000`.
