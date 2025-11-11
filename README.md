# Documentation Hub

A centralized documentation repository for hosting public documentation while keeping source code repositories private.

## 🚀 Purpose

This repository serves as a public-facing documentation hub for various projects, allowing:

- **Private Code**: Keep source code repositories private
- **Public Documentation**: Share user-facing documentation openly
- **Jekyll-Powered**: Static site generation with GitHub Pages
- **Multi-Project**: Support for multiple project documentation

## 📁 Structure

```
docs/
├── _config.yml              # Main Jekyll configuration
├── _layouts/               # Jekyll templates
├── _sass/                  # SCSS stylesheets
├── assets/                 # Static assets
├── index.md                # Homepage
├── cortex/                 # The Speddish Cortex docs
│   ├── _config.yml         # Project-specific config
│   ├── README.md           # Project overview
│   ├── privacy-policy.md   # Privacy policy
│   ├── terms-of-service.md # Terms of service
│   └── disclaimer.md       # Legal disclaimer
└── .nojekyll              # Disable Jekyll processing for GitHub Pages
```

## 🛠️ Setup

### Adding a New Project

1. Create a new directory: `mkdir new-project/`
2. Add project configuration: `new-project/_config.yml`
3. Create project documentation files
4. Update main `_config.yml` with project collection:
   ```yaml
   collections:
     new-project:
       output: true
       permalink: /:collection/:name/
       title: "New Project"
   ```

### GitHub Pages Setup

1. Push this repository to GitHub
2. Enable GitHub Pages in repository settings
3. Select source as "Deploy from a branch"
4. Choose `main` branch and `/ (root)` directory
5. Site will be available at `https://yourusername.github.io/docs/`

## 🎨 Customization

### Adding Projects

Edit `_config.yml` to add new projects:

```yaml
projects:
  new-project:
    title: "New Project"
    description: "Project description"
    url: "/new-project/"
    icon: "fas fa-star"
    color: "#10b981"
```

### Styling

- Edit `assets/css/style.scss` for custom styles
- Add new layouts to `_layouts/` directory
- Include additional SCSS files in `_sass/` directory

## 📝 Documentation Standards

### Front Matter

All documentation files should include appropriate front matter:

```yaml
---
layout: project
title: "Page Title"
description: "Page description for SEO"
project: "cortex"
last_modified: 2025-11-10
---
```

### Legal Documents

- Privacy policies must include data collection details
- Terms of service must cover user rights and responsibilities
- Disclaimers should cover limitations and liabilities

## 🚀 Deployment

### Local Development

```bash
# Install Jekyll and dependencies
gem install jekyll jekyll-feed jekyll-sitemap jekyll-seo-tag

# Serve locally
bundle exec jekyll serve

# Build for production
bundle exec jekyll build
```

### GitHub Actions

Add `.github/workflows/jekyll.yml` for automated builds:

```yaml
name: Jekyll Build
on:
  push:
    branches: [ main ]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Build Jekyll
      uses: actions/jekyll-build-pages@v1
      with:
        source: ./
        destination: ./_site
```

## 📄 License

This documentation repository is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/new-project`
3. Commit changes: `git commit -am 'Add new project documentation'`
4. Push to branch: `git push origin feature/new-project`
5. Submit a pull request

## 📞 Support

- **GitHub Issues**: Report bugs and request features
- **Email**: hello@docs.speddish.dev
- **Discussions**: Community support and questions