Below are two key files you can add to your repository: a README.md that outlines the repository’s focus and a USER-STORIES.md that defines your product and lists user stories meeting the INVEST criteria.

README.md

# Hugo Mock Landing Page for PlantPal

This repository hosts a mock landing page built with [Hugo](https://gohugo.io/) using the [hugo-bootstrap-theme](https://github.com/filipecarneiro/hugo-bootstrap-theme) as a submodule. The purpose of this project is to demonstrate how to customize a modern static site for a product, applying best practices in commit messaging, version control, and public code sharing.

## About PlantPal

**PlantPal** is a smart indoor gardening assistant designed to help plant owners care for their houseplants. Using IoT sensors, PlantPal monitors environmental conditions (like soil moisture, light, and temperature) and provides personalized care tips. It also features a community forum for sharing advice and inspiration, making plant care accessible and enjoyable.

## Key Features

- **Responsive & Modern Design:** Fully customizable landing page based on the Bootstrap theme.
- **Real-Time Monitoring:** Display live sensor data for each plant.
- **Personalized Care:** Provide tailored care recommendations based on sensor input.
- **Community Engagement:** Integrated community forum for tips, challenges, and social sharing.
- **Easy Onboarding:** A user-friendly setup wizard to get started quickly.

## Getting Started

1. **Clone the Repository (with submodules):**

   ```bash
   git clone --recurse-submodules https://github.com/<your-username>/hugo-mock-landing-page.git
   cd hugo-mock-landing-page
   code .

2. Install Dependencies:

    - Ensure Node.js is installed for theme builds.
    - Install any other dependencies required by the theme (see the theme’s README for details).

3. Run the Site Locally: `hugo server`. Open your browser and visit <http://localhost:1313/hugo-bootstrap-theme/> (or the port indicated in your terminal) to view the site.

4. Customize:

    - Edit content files (in Markdown) to update copy, images, and features.
    - Modify config.toml to include your name, GitHub Pages URL, and product details.
    - Remove or update extraneous example pages and posts.

5. Commit Guidelines: We follow a conventional commit style. Examples include:

    - feat: Add personalized care tips section
    - fix: Correct image paths in static assets
    - style: Update color scheme and logo
    - docs: Add installation instructions to README
    - chore: Remove unused example pages

6. Deploying to GitHub Pages: After running hugo to generate the static site, use the provided publish_to_gh_pages.sh script to push the output to the gh-pages branch.

Repository Structure

- config.toml: Main site configuration.
- content/: Markdown files for pages and posts.
- static/: Assets such as images and stylesheets.
- themes/hugo-bootstrap-theme/: Git submodule for the theme.
- USER-STORIES.md: Contains the user stories for PlantPal.
