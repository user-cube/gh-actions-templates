# Go GitHub Actions Workflows Templates

This directory contains GitHub Actions workflow templates specifically tailored for Go projects. The workflows are organized into different pipelines, each with its own purpose and configuration.

## Structure

The Go directory structure is organized as follows:

- **README.md**: This file providing an overview of the Go workflows and their contents.
- **pull-request**: Contains the workflow template for handling pull requests in Go projects. The `build-and-test.yml` file is the template for the pipeline.
- **release**: Contains the workflow template for handling releases in Go projects. The `release.yml` file is the template for the pipeline.

## Usage

1. Navigate to the desired pipeline directory (`pull-request` or `release`).
2. Copy the desired pipeline YAML file(s) into your project's `.github/workflows` directory.
3. Customize the pipeline as needed for your Go project requirements.
4. Commit and push the changes to your repository to trigger the pipeline(s).

For more detailed information about each pipeline, please refer to the README files in the respective directories.