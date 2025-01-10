
Note: bitbucket-piplines.yml file

# CI/CD Pipeline Overview
    The CI/CD pipeline automates the following:
    1. Code Integration: Ensures code quality through linting and formatting checks.
    2. Automated Testing: Runs unit and integration tests to verify functionality.
    3. Containerization: Builds and pushes Docker images to a container registry.
    4. Kubernetes Deployment: Deploys the Docker image to a Kubernetes cluster.

## Steps

1. **Lint & Format**:
   - Tools Used: ESLint and Prettier.
   - Validates code quality and formatting using ESLint and Prettier.
   Commands:
        npx eslint . --fix: Fixes linting issues automatically.
        npx prettier --check .: Checks formatting consistency.

2. **Run Unit Tests**:
    Tools Used: Jest
   -  Validates the code's functionality by running unit tests.
   Commands:
    npm install: Installs dependencies for the tests.
    npm test: Executes the test suite.

3. **Docker Build & Push**:
   - Packages the application into a Docker container for deployment.
   Tools Used: Docker CLI.
    Commands:
        docker build: Builds the Docker image using the Dockerfile.
        docker tag: Tags the image with the build number for versioning.
        docker push: Pushes the tagged image to the Docker registry.

4. **Kubernetes Deployment**:
    Tools Used: kubectl CLI.
   - Deploys the Docker image to a Kubernetes cluster.
    Commands:
       - pipe: atlassian/kubectl-run:1.1.2 :// Runs the kubectl command using a preconfigured Atlassian Bitbucket Pipe
       KUBECTL_COMMAND: 'apply' :// Specifies the kubectl command to execute.
       RESOURCE_PATH: 'deployment.yml'  :// Points to the resource configuration file (deployment.yml) that kubectl apply should use.
       