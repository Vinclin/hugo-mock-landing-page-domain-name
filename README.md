# Hugo Mock Landing Page (Auto-Deployed)

This repository is a Hugo-based static website that is automatically built and deployed to GitHub Pages using GitHub Actions. Every time changes are pushed to the **main** branch, the workflow builds the site and publishes it to the **gh-pages** branch.

## GitHub Actions Deployment Workflow

The deployment process is defined in the workflow file: **.github/workflows/gh-pages-deployment.yaml**. The workflow consists of the following key steps:

1. **Checkout Source Code**
   - Uses the [`actions/checkout@v3.5.1`](https://github.com/actions/checkout) action to clone the repository.
   - Ensures submodules (like the Hugo theme) are included and that full history is fetched for accurate metadata.

2. **Initialize Hugo Environment**
   - Sets up Hugo using [`peaceiris/actions-hugo@v2.6.0`](https://github.com/peaceiris/actions-hugo) with the specified version (`0.123.4`) and enables the extended version.

3. **Build the Site**
   - Runs `hugo -D --gc --minify` to generate static files.
   - The flags:
     - `-D` includes content marked as drafts.
     - `--gc` performs garbage collection.
     - `--minify` reduces the size of HTML, CSS, and JS files.

4. **Deploy to GitHub Pages**
   - Uses [`peaceiris/actions-gh-pages@v3.9.3`](https://github.com/peaceiris/actions-gh-pages) to deploy the site.
   - Publishes the generated files to the **gh-pages** branch using the provided `GITHUB_TOKEN`.

## Repository and Workflow Settings

- **Repository Settings:**
  - GitHub Actions is configured with **read and write permissions** to allow deployments.
  - GitHub Pages is set to use the **gh-pages** branch as its publishing source.
  - The default permissions are set to allow all actions and reusable workflows.

- **Configuration Adjustments:**
  - The `baseURL` in the configuration file (`config.toml` or `config.yaml`) has been updated to:

    ``` bash
    baseURL = 'https://<GitHub username>.github.io/hugo-mock-landing-page-autodeployed/'
    ```

  - Replace `<GitHub username>` with your actual GitHub username.

## Continuous Deployment Process

- **Trigger:** Every push to the **main** branch triggers the workflow.
- **Result:** Once the GitHub Actions workflow completes successfully, the updated website is deployed and available at: [site](https://.github.io/hugo-mock-landing-page-autodeployed/)
- **Troubleshooting:** If you experience a 404 error after deployment, wait a few minutes and refresh your browserrefresh your browser for a few minutes. If the workflow fails, double-check the GitHub Actions permissions (ensuring read/write access).

## Workflow Explanation Transcript

During setup, we consulted with Claude for a deeper understanding of the GitHub Actions YAML file. Below is an excerpt from that conversation:

> **Claude explained:**  
> "The workflow is structured into clear steps: first, it checks out the repository (including submodules), then it initializes the Hugo environment by setting the correct version and configuration, compiles the website into static files, and finally deploys those files to GitHub Pages. This automation not only streamlines the deployment process but also ensures that every update on the main branch is immediately reflected on the live site."

## Contributing

If you wish to contribute or suggest improvements:

- Open an issue on the repository using the provided link.
- Feel free to fork the repository and submit pull requests.

---

This documentation should help you (and others) understand the deployment process and facilitate troubleshooting if needed. Commit this updated **README.md** along with the workflow explanation transcript (e.g., as a PDF) to ensure all information is centralized in the repository.
