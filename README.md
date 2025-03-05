# Postman API Tests with Newman

This repository contains a GitHub Actions workflow to run Postman API tests using Newman, an open-source command-line collection runner for Postman. The workflow runs the API tests automatically on each push to the `main` branch, as well as on pull requests and manually via the workflow dispatch.

## Prerequisites

Before using this workflow, ensure the following:

1. **Postman Collection**: You should have a Postman collection file (`GoRestCollection.json`) in your repository that contains the API tests.
2. **Postman Environment**: You should have a Postman environment file (`GoRestEnvironment.json`) in your repository for any environment variables required during the tests (e.g., API keys, URLs).
3. **GitHub Actions**: You must have access to GitHub Actions to run the workflow on push or pull request events.

## Workflow Overview

This workflow automates the following steps:

1. **Checkout Repository**: The repository is checked out to ensure the latest version of the code is available.
2. **Install Node.js**: The required Node.js version is set up.
3. **Install Newman and Reporter**: Newman and the Newman HTML reporter are installed globally.
4. **Run API Tests**: The Postman collection is run using Newman, and the results are outputted in both CLI and HTML formats.
5. **Upload Test Report**: The test results in HTML format are uploaded as an artifact, making them available for download.
