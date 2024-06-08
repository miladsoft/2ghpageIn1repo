### HTML File Deployment

This repository contains the configuration for automating the deployment of a simple HTML file to two separate domains using GitHub Actions.

#### Deployment Overview

The deployment process is configured to publish the HTML file to the following domains:
- `test1.seniorblockchain.io`
- `test2.seniorblockchain.io`

#### GitHub Actions Workflow

The GitHub Actions workflow (`deploy.yml`) automates the following steps:
1. **Checkout Repository**: Retrieve the latest code from the `main` branch.
2. **Setup .NET Core**: Prepare the environment with .NET Core 8.0.
3. **Publish the Project**: Compile the project and output the build files.
4. **Setup Files**:
   - Copy `index.html` to `404.html` to handle 404 errors gracefully.
   - Create a `.nojekyll` file to bypass Jekyll processing.
   - Create a `CNAME` file for each domain.
5. **Minify Assets**: Optimize JS and CSS files to reduce load times.
6. **Deploy to GitHub Pages**:
   - For `test1.seniorblockchain.io`: Publish to the `gh-pages-test1` branch.
   - For `test2.seniorblockchain.io`: Publish to the `gh-pages-test2` branch.

#### Instructions

1. **Create the Workflow File**:
   - Save the provided YAML content in `.github/workflows/deploy.yml`.

2. **DNS Configuration**:
   - Ensure that DNS records for `test1.seniorblockchain.io` and `test2.seniorblockchain.io` are correctly pointed to GitHub Pages.

3. **Push Changes**:
   - Commit and push the changes to the `main` branch.
   - The GitHub Actions workflow will trigger automatically on a push to `main`, deploying the project to both domains.

4. **Verify Deployment**:
   - Once the workflow completes, verify that the sites are correctly deployed by visiting `test1.seniorblockchain.io` and `test2.seniorblockchain.io`.

This setup ensures that the HTML file will be served from both domains, with optimized assets and proper handling of domain-specific configurations.
