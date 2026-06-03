# revys.net — Personal Website

A personal website built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme, hosted on [GitHub Pages](https://pages.github.com/).

## Quick Start

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) (v0.145.0+)
- Git

### Local Development

```bash
# Clone with submodules (for the theme)
git clone --recurse-submodules https://github.com/Revys17/Revys17.github.io.git
cd Revys17.github.io

# Start the dev server
hugo server -D
```

The site will be available at `http://localhost:1313/`.

## Content Management

### Adding a Blog Post

1. Create a new markdown file in `content/blog/`:

```bash
hugo new content blog/my-new-post.md
```

2. Edit the file. The front matter looks like this:

```yaml
---
title: "My New Post"
date: 2026-04-01
draft: false
tags: ["topic1", "topic2"]
summary: "A brief summary that appears in the blog list."
---

Your content here, written in Markdown.
```

3. Set `draft: false` when you're ready to publish.

4. Commit and push:

```bash
git add .
git commit -m "New post: My New Post"
git push
```

GitHub Actions will automatically build and deploy the site.

### Updating Your Resume

Edit `content/resume.md`. The page uses standard Markdown — update the sections with your actual experience, education, and skills.

### Updating Publications

Edit `content/publications.md`. Add new entries following the existing format:

```markdown
## 2026

**[Paper Title](https://doi.org/your-doi)**
*Your Name*, Co-Author Name
*Conference or Journal Name*

> Brief description of the paper.
```

### Updating Your Photo

Replace `static/images/profile-placeholder.svg` with your actual photo. Recommended:

- Use a square image (e.g., 400×400 px)
- Name it `profile.jpg` or `profile.png`
- Update the `imageUrl` in `hugo.toml` under `[params.profileMode]`:

```toml
imageUrl = "/images/profile.jpg"
```

### Updating Site Info

Edit `hugo.toml` to change:

- **Site title**: `title` at the top
- **Tagline**: `subtitle` under `[params.profileMode]`
- **Social links**: `[[params.socialIcons]]` entries
- **Menu items**: `[[menu.main]]` entries

## Deployment

The site auto-deploys via GitHub Actions on every push to `main`. The workflow:

1. Installs Hugo Extended
2. Builds the site with `hugo --gc --minify`
3. Deploys to GitHub Pages

### Custom Domain Setup

The `static/CNAME` file is set to `revys.net`. For DNS configuration:

1. In Cloudflare, add a CNAME record: `revys.net` → `Revys17.github.io`
2. In the GitHub repo settings → Pages, set the custom domain to `revys.net`
3. Enable "Enforce HTTPS"

## Project Structure

```
.
├── .github/workflows/deploy.yml  # GitHub Actions deployment
├── content/
│   ├── blog/                     # Blog posts (add .md files here)
│   │   ├── _index.md             # Blog listing page
│   │   └── hello-world.md        # Example post
│   ├── resume.md                 # Resume/CV page
│   └── publications.md           # Publications page
├── layouts/
│   └── 404.html                  # Custom 404 page
├── static/
│   ├── CNAME                     # Custom domain config
│   └── images/
│       └── profile-placeholder.svg
├── hugo.toml                     # Site configuration
└── README.md
```

## License

Content is © Revys. The Hugo framework and PaperMod theme have their own licenses.
