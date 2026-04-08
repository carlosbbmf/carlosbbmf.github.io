# My Academic Site

Personal research hub built with [Quarto](https://quarto.org) and hosted on GitHub Pages.

---

## Structure

```
academic-site/
├── _quarto.yml              # Site configuration
├── custom.scss              # Styles
├── index.qmd                # About / Home
├── research.qmd             # Research projects
├── cv.qmd                   # Curriculum Vitae
├── posts/
│   ├── index.qmd            # Blog listing page
│   ├── example-post.qmd     # Text post example
│   └── example-r-post.qmd  # Technical post with R code
├── assets/
│   ├── profile.jpg          # Your profile photo
│   └── cv.pdf               # PDF version of your CV
└── .github/
    └── workflows/
        └── deploy.yml       # Auto-deploy to GitHub Pages
```

---

## Local Setup

### 1. Install Quarto
Download from [quarto.org/docs/get-started](https://quarto.org/docs/get-started/)

### 2. Install R packages used in posts
```r
install.packages(c("lme4", "ggplot2", "dplyr", "ggrepel"))
```

### 3. Preview locally
```bash
quarto preview
```

### 4. Build the site
```bash
quarto render
```
Output goes to the `docs/` folder.

---

## Deploying to GitHub Pages

1. Push this repo to GitHub
2. Go to **Settings → Pages**
3. Set source to **GitHub Actions**
4. Push any commit — the workflow in `.github/workflows/deploy.yml` handles the rest

Your site will be live at `https://yourusername.github.io/your-repo-name/`

---

## Customizing

| What to change | Where |
|---|---|
| Name, institution, links | `_quarto.yml` and `index.qmd` |
| Colors and fonts | `custom.scss` |
| Research projects | `research.qmd` |
| CV | `cv.qmd` |
| New blog post | Add a `.qmd` file inside `posts/` |
| Profile photo | Replace `assets/profile.jpg` |

---

## Writing a New Post

Create a file `posts/my-post-title.qmd` with this header:

```yaml
---
title: "Your Post Title"
date: "2025-07-01"
description: "One-line summary shown in the listing."
categories: [methods, R]   # choose freely
---
```

Then write in Markdown. R code chunks work exactly as in R Markdown:

````markdown
```{r}
#| label: my-plot
#| fig-cap: "Caption here"

plot(1:10)
```
````
