# Sayantan Banerjee — Jekyll academic website

This site runs on **GitHub Pages + Jekyll**. You can edit content without touching HTML.

## Publishing

1. Create a **public** repository named `YOURUSERNAME.github.io`.
2. Upload **the contents** of this folder to the repository root (not the folder itself).
3. In Settings → Pages choose **Deploy from a branch**, `main`, `/(root)`.
4. Wait for GitHub Pages to build and visit `https://YOURUSERNAME.github.io`.
5. **Delete the old `.nojekyll` file** if you are replacing your previous static website. This package does not contain it.

## Most common updates

- Add a paper: edit `_data/publications.yml`; add a new item with `year`, `title`, `authors`, `journal`, `url`.
- Add news: edit `_data/news.yml`; use `date`, `text`, `url`. News appears automatically on the homepage.
- Edit your biography, CV, affiliation, or photo path: `_data/profile.yml`.
- Edit courses: `_data/teaching.yml`.
- Edit awards: `_data/awards.yml`.
- Edit grants, working papers, students: their matching files in `_data/`.
- Edit education, service, and contact: `_data/education.yml`, `_data/services.yml`, `_data/contact.yml` (these preserve original page HTML inside a YAML field).
- Change colors, spacing, and typography: `assets/academic.css`.

The five most recent publications are **automatically generated** on the homepage; publications are sorted newest-first on the research page. There is a working search/year filter.

## Photo

Upload `Sayantan.jpg` to `assets/` with exactly that spelling. The image is not included in this package because it was uploaded to your GitHub repository, not to this conversation. The site will display a placeholder message until you add it.

## Important

This conversion is based on the previously generated website content. Please review entries, dates, URLs, and current roles before publishing. The news file contains a sample welcome message; replace it with genuine announcements. Some paper URLs are Google Scholar search links, not verified DOI URLs.

GitHub Pages automatically processes `_data`, `_includes`, and `_layouts`. Do not add `.nojekyll`.
