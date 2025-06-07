# My Jekyll Portfolio & Blog Theme (Catppuccin Styled)

[![License: CC BY 4.0](https://licensebuttons.net/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0/)
<!-- GitHub Actions Workflow Status Badge - Replace YOUR_USERNAME and YOUR_REPONAME -->
<!-- ![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/YOUR_USERNAME/YOUR_REPONAME/jekyll.yml?branch=main&logo=github) -->

A responsive, multilingual portfolio and blog theme for Jekyll, styled with the Catppuccin Mocha theme and Tailwind CSS. Built to be easily customizable and deployed on GitHub Pages using GitHub Actions. This theme is initially configured for English (default) and Turkish, but can be extended to support more languages.

[View Demo](https://sahinmuhammetabdullah.github.io/portfolio/) <!-- Update with your demo link -->
| [Türkçe Açıklama (Turkish Documentation)](README_tr.md)

## ✨ Features

*   **Multilingual Support:** Easily manage content in multiple languages using Jekyll Polyglot. Configured પાણીof-the-box for English (default) and Turkish, extensible for more.
*   **Responsive Design:** Looks great on desktops, tablets, and mobile devices.
*   **Catppuccin Mocha Theming:** Beautiful, soothing dark theme.
*   **Tailwind CSS (CDN):** Utility-first CSS framework for easy customization via CDN.
*   **Project Showcase:** Dedicated section to display your projects with details in a modal.
    *   Cover images for project cards (fallback to color gradients).
    *   Markdown support for project descriptions, allowing rich text and images within modals.
*   **Font Awesome Icons:** For social media links and project card icons.
*   **SEO Optimized:** With `jekyll-seo-tag`.
*   **RSS Feed:** With `jekyll-feed`.
*   **Sitemap:** With `jekyll-sitemap`.
*   **Customizable Data Files:** Easily update profile information, social links, navigation, and UI strings via YAML files in the `_data` directory for each supported language.
*   **GitHub Pages Ready:** Includes a GitHub Actions workflow for automatic building and deployment.

## 🚀 Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes, or for deploying your own version.

### Prerequisites

*   **Ruby:** [Check version](https://www.ruby-lang.org/en/documentation/installation/) (e.g., 3.0.x, 3.1.x as per `Gemfile` and workflow)
*   **Bundler:** (`gem install bundler`)
*   **Jekyll:** (`gem install jekyll`)
*   (Optional) Node.js and npm/yarn if you plan to install Tailwind CSS locally and use its full capabilities (e.g., `@tailwindcss/typography` plugin).

### Installation & Local Development

1.  **Fork or Clone the Repository:**
    ```bash
    git clone https://github.com/SahinMuhammetAbdullah/portfolio.git # Replace with your fork if applicable
    cd portfolio
    ```

2.  **Install Dependencies:**
    This command reads the `Gemfile` and installs all necessary Ruby gems.
    ```bash
    bundle install
    ```

3.  **Serve the Site Locally:**
    This command builds the site and starts a local web server.
    ```bash
    bundle exec jekyll serve --livereload --baseurl ""
    ```
    *   Your site should now be running at `http://localhost:4000/`.
    *   The `--livereload` flag automatically refreshes the page when you make changes.
    *   `--baseurl ""` overrides the `baseurl` in `_config.yml` for local development, ensuring links work correctly when serving from the root.
    *   The default language (English) will be served at `http://localhost:4000/`.
    *   Other languages will be at their respective paths (e.g., Turkish: `http://localhost:4000/tr/`).

### ⚙️ Build and Deployment with GitHub Actions

This repository is configured for easy deployment to GitHub Pages using a predefined **GitHub Actions workflow**.

**How it Works:**

1.  **Workflow File:** The deployment process is defined in `.github/workflows/jekyll.yml`. This file tells GitHub Actions how to build and deploy your Jekyll site.
2.  **Trigger:** The workflow is automatically triggered when you `push` changes to your `main` (or `master`) branch.
3.  **Build Process:**
    *   GitHub Actions sets up a virtual environment (Ubuntu).
    *   It checks out your repository's code.
    *   It sets up the Ruby environment and installs all dependencies from your `Gemfile` using `bundle install`. This includes `jekyll-polyglot` and other custom plugins.
    *   It then runs `bundle exec jekyll build` to generate your static site into an `_site` directory. The `baseurl` configured in `_config.yml` (or determined by `actions/configure-pages`) is used here.
4.  **Deployment to GitHub Pages:**
    *   The contents of the `_site` directory are uploaded as a "Pages artifact".
    *   This artifact is then deployed to your GitHub Pages site.

**Steps for Forked Repositories:**

If you have forked this repository and want to deploy it to your own GitHub Pages:

1.  **Update `_config.yml`:**
    *   Set `url` to your GitHub Pages root (e.g., `https://yourusername.github.io`).
    *   Set `baseurl`:
        *   If your repository is named `yourusername.github.io`, set `baseurl: ""`.
        *   If your repository is named `my-portfolio`, set `baseurl: "/my-portfolio"`.
    *   Update other site-specific details (`title`, `author`, `email`, etc.).

2.  **Configure GitHub Pages Source:**
    *   In your forked repository, go to **Settings** > **Pages**.
    *   Under "Build and deployment", for the **Source**, select **GitHub Actions**.
    *   This tells GitHub Pages to use the output from your `deploy.yml` workflow instead of trying to build the site itself (which wouldn't support custom plugins like `jekyll-polyglot`).

3.  **First Deployment Approval (If Needed):**
    *   Sometimes, the first time a GitHub Actions workflow tries to deploy to a GitHub Pages environment, it might require a manual approval.
    *   If your workflow run palavrasin the "Actions" tab, check for a "Waiting for approval" status or a "Review deployments" button. If present, approve it to proceed.

4.  **Push Changes:**
    *   Commit and push your changes (especially to `_config.yml`) to your `main` branch. This will trigger the GitHub Actions workflow, which will build and deploy your site. Your site should then be live at the URL specified in your Pages settings.

### Troubleshooting: Automatic Deployment Not Working

If, after configuring GitHub Pages to use "GitHub Actions" as the source, the deployment workflow (`.github/workflows/deploy.yml`) does not trigger automatically on push, or if GitHub Pages still seems to be attempting its own build, you might need to manually enable or re-trigger the workflow for the Pages environment.

Follow these steps if your site is not deploying automatically via the custom GitHub Action:

1.  **Navigate to GitHub Pages Settings:**
    *   In your repository, go to **Settings** > **Pages**.
    *   Ensure "Build and deployment" source is set to **GitHub Actions**.

2.  **Access Workflow Runs for Pages:**
    *   If there's an indication that workflows need to be enabled or there are issues, you might see a message or a link like **"View workflow runs"** (or similar, pertaining to Pages). Click on it.
    ![picture](/assets/1.png)


3.  **Enable Workflows (If Prompted):**
    *   You might be taken to a page asking you to confirm that you understand and want to enable workflows for GitHub Pages deployment.
    *   Click on **"I understand my workflows, go ahead and enable them"** (or a similar confirmation button).
    ![picture](/assets/2.png)

4.  **Manually Run the Deployment Workflow:**
    *   Go to the **Actions** tab in your repository.
    *   In the left sidebar, find and click on your deployment workflow (e.g., **"Jekyll Site Build and GitHub Pages Deployment"** or "Build and Deploy").
    ![picture](/assets/3.png)
    *   You should see a **"Run workflow"** button, usually on the right side. Click this button.
    *   A dropdown might appear asking which branch to run from; select your main branch (e.g., `main`) and click the green **"Run workflow"** button.
    ![picture](/assets/4.png)

5.  **Confirm Workflow Request:**
    *   After successfully triggering the workflow, you should see a confirmation message like **"Workflow run was successfully requested."**
    ![picture](/assets/5.png)
    *   You can now monitor the progress of this manually triggered workflow run. Once it completes successfully, your site should be deployed to GitHub Pages.

This manual trigger often helps GitHub Pages correctly associate your custom workflow with its deployment process. Subsequent pushes to your configured branch should then trigger the workflow automatically.

## 🛠️ Customization

*   **Site Configuration (`_config.yml`):**
    *   Update `title`, `author`, `description`, `email`, `url`, `baseurl`, `github_username`.
    *   **Jekyll Polyglot:** `languages` (add new language codes here, e.g., `["en", "tr", "fr"]`), `default_lang`, `default_lang_in_url`.
    *   Footer details: `technologies_used`, `license_name`, etc.

*   **Adding a New Language (e.g., French "fr"):**
    1.  Add `"fr"` to the `languages` list in `_config.yml`.
    2.  Create `_data/navigation.yml` (copy from `navigation.yml with en:` and translate).
    3.  In `_data/translations.yml`, add an `fr:` section with all UI strings translated (copy from `en:` section and translate).
    4.  In `_data/profile.yml`, add an `fr:` section with profile details translated.
    5.  For each project in `_projects/en/`, create a corresponding file in `_projects/fr/` (e.g., `_projects/fr/my-project.md`) with translated content. Ensure the `id` front matter field remains the same.
    6.  The language switcher in the header will automatically include "fr".

*   **Profile, Navigation, UI Strings, Social Links:** Edit files in the `_data` directory (`profile.yml`, `navigation.xx.yml`, `translations.yml`, `social.yml`).

*   **Projects (`_projects/`):**
    *   Maintain subfolders for each language (e.g., `en/`, `tr/`).
    *   Project `.md` files use front matter for metadata (`id`, `title`, `cover_image`, `tags`, etc.) and Markdown for the detailed description in the modal.
    *   Ensure `id` is consistent across language versions of the same project.

*   **Styling (`assets/css/style.css`):** Add custom CSS or overrides.
*   **Favicons & Manifest:** Update files in `assets/images/favicons/` and the root `manifest.json`. Ensure paths in `_includes/head.html` and `manifest.json` are correct.

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improving this theme, feel free to:
1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📜 License

This project is licensed under the **CC BY 4.0 License**. See the [LICENSE](LICENSE) file for more details.

## 🙏 Acknowledgements

*   [Jekyll](https://jekyllrb.com/)
*   [Jekyll Polyglot](https://github.com/untra/jekyll-polyglot)
*   [Tailwind CSS](https://tailwindcss.com/)
*   [Font Awesome](https://fontawesome.com/)
*   [Catppuccin Theme Palette](https://github.com/catppuccin/catppuccin)
*   Designed by **{{ site.designer_name }}**. This theme is licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/) ({{ site.license_url }}). You are free to use, share, and adapt it, provided you give appropriate credit to **{{ site.designer_name }}** as the original designer. This typically means retaining the "Design by..." credit in the footer or a similar acknowledgements section.

---

## Türkçe Açıklama (Turkish Documentation)

Bu projenin Türkçe kullanım kılavuzu ve açıklamaları için lütfen [README_tr.md](README_tr.md) dosyasına bakın.

(For Turkish documentation and usage guide for this project, please see the [README_tr.md](README_tr.md) file.)