# Build and Test on Pull Request

This GitHub Actions workflow automates the build and testing process for pull requests targeting the `main` branch of your repository.

## Workflow Overview

### Triggers
- **Event:** This workflow triggers on pull requests to the `main` branch.

### Permissions
- **Contents:** Read access is required to checkout the repository contents.
- **Pull Requests:** Read access is required to fetch pull request information.

### Jobs
- **build:** This job is responsible for building and testing the codebase.
  - **Runs on:** Ubuntu latest environment.
  - **Steps:**
    1. **Checkout:** Fetches the repository contents including history.
    2. **Set up Go:** Configures the Go environment with the specified version.
    3. **Run Tests:** Executes all tests in verbose mode.
    4. **golangci-lint:** Utilizes the `golangci/golangci-lint-action` to perform linting.
    5. **Run Linters:** Executes linting using golangci-lint.
    6. **Build:** Compiles the Go code.

## Usage
- **Requirements:** Ensure that Go is installed and configured on the runner environment.
- **Configuration:** Adjust the workflow file according to your project requirements, such as changing the Go version or adding additional steps for specific build or test tasks.

### Running golangci-lint Locally
To use `golangci-lint` locally, follow these steps:

1. Install `golangci-lint` using the following command:
   ```bash
   curl -sSfL https://raw.githubusercontent.com/golangci/golangci-lint/master/install.sh | sh -s -- -b $(go env GOPATH)/bin v1.58.1
   ```

2. Verify the installation by checking the version:
   ```bash
   golangci-lint --version
   ```

3. Once installed, you can use golangci-lint to lint your Go codebase by running:
   ```bash
   golangci-lint run
   ```

## Notes
- This workflow assumes a Go-based project and utilizes Go modules for dependency management.
- Adjust the version numbers of actions used (e.g., `actions/setup-go@v5`, `golangci/golangci-lint-action@v6`) as needed based on the latest releases.