# Matthias Bitzer - Personal Website

Personal website featuring AI/ML blog posts, AI art gallery, and publications. Built with Jekyll and hosted on GitHub Pages.

## About

This site showcases:
- **Blog**: Articles about AI, machine learning, and data science
- **AI Art Gallery**: AI-generated art focused on meditation and Buddhism
- **Publications**: Academic and technical publications
- **About**: Personal bio and contact information

## Technology Stack

- **Framework**: Jekyll 4.3
- **Theme**: Minima (customized)
- **Hosting**: GitHub Pages
- **Content**: Markdown

## Local Development

### Prerequisites

- Ruby (version 2.7 or higher)
- Bundler (`gem install bundler`)

### Setup

1. Clone the repository
2. Install dependencies:
   ```bash
   bundle install
   ```
3. Run the development server:
   ```bash
   bundle exec jekyll serve
   ```
4. Visit `http://localhost:4000` in your browser

To preview with the same base path as GitHub Pages (e.g. `https://USERNAME.github.io/homepage/`), run:
```bash
bundle exec jekyll serve --baseurl /homepage
```
Then open `http://localhost:4000/homepage/`.

### Building for Production

```bash
bundle exec jekyll build
```

The site will be generated in the `_site` directory.

## Content Structure

```
homepage/
├── _posts/           # Blog posts (Markdown)
├── _layouts/         # Page templates
├── _includes/        # Reusable components
├── assets/           # CSS, images, and other static files
├── index.md          # Homepage
├── blog.md           # Blog listing page
├── gallery.md        # AI Art Gallery
├── publications.md   # Publications page
└── about.md          # About page
```

## Deployment

This site is automatically deployed to GitHub Pages when changes are pushed to the main branch.

## License

Copyright © 2026 Matthias Bitzer. All rights reserved.
