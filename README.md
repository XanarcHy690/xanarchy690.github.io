# My Jekyll Portfolio & Blog Theme (Catppuccin Styled)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
<!-- İsterseniz buraya GitHub Actions build status badge'i ekleyebilirsiniz -->
<!-- ![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/YourUsername/YourRepoName/deploy.yml?branch=main) -->

A responsive, a bilingual (English & Turkish) portfolio and blog theme for Jekyll, styled with the Catppuccin Mocha theme and Tailwind CSS. Built to be easily customizable and deployed on GitHub Pages.

[View Demo](https://sahinmuhammetabdullah.github.io/portfolio/en/) <!-- Kendi demo linkinizle değiştirin -->
| [Türkçe Açıklama (Turkish Documentation)](#türkçe-açıklama-turkish-documentation) <!-- README_tr.md'ye link -->

## ✨ Features

*   **Bilingual Support:** Easily manage content in English (default) and Turkish using Jekyll Polyglot.
*   **Responsive Design:** Looks great on desktops, tablets, and mobile devices.
*   **Catppuccin Mocha Theming:** Beautiful, soothing dark theme.
*   **Tailwind CSS:** Utility-first CSS framework for easy customization.
*   **Project Showcase:** Dedicated section to display your projects with details in a modal.
    *   Cover images for project cards (fallback to color gradients).
    *   Markdown support for project descriptions, allowing rich text and images within modals.
*   **Font Awesome Icons:** For social media links and project card icons.
*   **SEO Optimized:** With `jekyll-seo-tag`.
*   **RSS Feed:** With `jekyll-feed`.
*   **Sitemap:** With `jekyll-sitemap`.
*   **Customizable Data Files:** Easily update profile information, social links, navigation, and UI strings via YAML files in the `_data` directory.
*   **GitHub Pages Ready:** Includes a GitHub Actions workflow for automatic deployment.

## 🚀 Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes, or for deploying your own version.

### Prerequisites

*   **Ruby:** [Check version](https://www.ruby-lang.org/en/documentation/installation/) (Jekyll's requirement, e.g., 3.0.x)
*   **Bundler:** (`gem install bundler`)
*   **Jekyll:** (`gem install jekyll`)
*   (Optional) Node.js and npm/yarn if you plan to customize Tailwind CSS extensively and build it locally. Currently, this theme uses the Tailwind CSS CDN for simplicity.

### Installation & Local Development

1.  **Fork or Clone the Repository:**
    ```bash
    git clone https://github.com/SahinMuhammetAbdullah/portfolio.git
    cd portfolio
    ```

2.  **Install Dependencies:**
    ```bash
    bundle install
    ```

3.  **Serve the Site Locally:**
    ```bash
    bundle exec jekyll serve --livereload
    ```
    Your site should now be running at `http://localhost:4000`. The `--livereload` flag will automatically refresh the page when you make changes. By default, it will serve the English version.
    *   To view the Turkish version: `http://localhost:4000/tr/`

### Deployment

This repository includes a GitHub Actions workflow (`.github/workflows/deploy.yml`) that automatically builds and deploys the site to GitHub Pages when you push to the `main` branch.

1.  Ensure your repository settings for GitHub Pages are configured to use "GitHub Actions" as the source.
2.  Update the `url` and `baseurl` in `_config.yml` to match your GitHub Pages URL (e.g., `url: https://yourusername.github.io`, `baseurl: /your-repo-name`).

## 🛠️ Customization

Most customizations can be done by editing YAML files in the `_data` directory and Markdown files for content.

*   **Site Configuration (`_config.yml`):**
    *   `title`, `author`, `description`, `email`
    *   `url`, `baseurl` (CRITICAL for deployment)
    *   `github_username`
    *   Jekyll Polyglot settings: `languages`, `default_lang`, `default_lang_in_url`
    *   Theme colors for PWA: `theme_color`, `background_color`, `ms_tile_color`
    *   `technologies_used`, `license_name`, `license_url`, `repository_url`, `designer_name`, `designer_url` for the footer.

*   **Profile Information (`_data/profile.yml`):**
    *   Contains language-specific profile details like `tagline`, `greeting_intro`, `about_title`, `about_bio`, `skills`, and `footer_copyright` template.
    *   Update your `avatar` path here.

*   **Navigation Links (`_data/navigation.tr.yml`, `_data/navigation.en.yml`):**
    *   Define the main navigation links (title and URL) for each language.

*   **UI Strings (`_data/translations.yml`):**
    *   Contains all general UI text strings (section titles, button labels, etc.) for both `tr` and `en` under their respective language keys.

*   **Social Links (`_data/social.yml`):**
    *   Define your social media links, including `name`, `url`, and `icon_class` (Font Awesome).

*   **Projects (`_projects/`):**
    *   Create subfolders `tr` and `en` inside `_projects`.
    *   For each project, create a `.md` file in both language folders (e.g., `_projects/tr/my-project.md` and `_projects/en/my-project.md`).
    *   Ensure the `id` field in the front matter is THE SAME for both language versions of a project.
    *   Customize `title`, `short_description`, `tags`, `cover_image`, `icon_class`, `github_url`, `live_url`.
    *   The content after the front matter (---) is Markdown for the project's detailed description, which appears in the modal. You can include images here using Markdown syntax: `![Alt text]({{ '/assets/images/your-image.jpg' | relative_url }})`.

*   **Styling (`assets/css/style.css`):**
    *   Contains custom CSS, including styles for Markdown-generated HTML in modals and scrollbar styling.
    *   Tailwind CSS is primarily used via CDN, but you can add overrides or new styles here.

*   **Favicons:**
    *   Place your favicon files (e.g., `favicon.ico`, `apple-touch-icon.png`, various `favicon-*.png`) in `assets/images/favicons/`.
    *   Update paths in `_includes/head.html` and `manifest.json` (if you moved them from the root).
    *   The `manifest.json` in the root directory configures PWA-like features. Ensure paths alegriaare correct.

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improving this theme, feel free to:
1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📜 License

This project is licensed under the **{{ site.license_name | default: "MIT License" }}**. See the [LICENSE](LICENSE) file for more details.

## 🙏 Acknowledgements

*   [Jekyll](https://jekyllrb.com/)
*   [Jekyll Polyglot](https://github.com/untra/jekyll-polyglot)
*   [Tailwind CSS](https://tailwindcss.com/)
*   [Font Awesome](https://fontawesome.com/)
*   [Catppuccin Theme Palette](https://github.com/catppuccin/catppuccin)
*   Your Name (as the designer - this will be automatically picked up from `_config.yml` if you use `{{ site.designer_name }}`)

---

## Türkçe Açıklama (Turkish Documentation)

Bu projenin Türkçe kullanım kılavuzu ve açıklamaları için lütfen [README_tr.md](README_tr.md) dosyasına bakın.

(For Turkish documentation and usage guide for this project, please see the [README_tr.md](README_tr.md) file.)