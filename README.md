
# Finel_Project_Jenkins

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Pipeline Stages](#pipeline-stages)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

## Overview
This project involves building a Docker image, pushing it to a repository, and running the Docker container using Jenkins. The Jenkins pipeline is designed to automate the process, ensuring a streamlined CI/CD workflow.

## Prerequisites
- Jenkins
- Docker
- A Git repository to push the Docker image to

## Installation
1. Clone the repository to your local machine.
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

Ensure you have Jenkins and Docker installed and running on your machine.
Configure Jenkins with Docker plugin.

## Usage
1. Set up your Jenkins pipeline with the provided `Jenkinsfile`.
2. Ensure your Dockerfile is present in the root directory of your project.
3. Trigger the Jenkins pipeline to start the process.

## Pipeline Stages

### 1. Starting
- Initial stage to log the start of the pipeline.
- Output messages indicating the start and end of this stage.

### 2. Build
- Builds the Docker image using the Dockerfile.
- Tags the Docker image with the name specified in the `IMAGE_NAME` environment variable.
- Logs the name of the Docker container to be created.

### 3. Test all env variables
- Logs and tests all environment variables.
- Checks if a Docker container with the name specified in `CON_NAME` exists.
  - If the container exists, stops and removes it.

### 4. Deploy
- Runs the Docker container in detached mode.
- Maps port 8000 of the host to port 8000 of the container.
- Logs the deployment process.

### 5. Checks
- Checks the health of the Docker container.
- Stops and removes the container after a brief pause.
- Logs the status and existence of the container.

## Configuration
### Jenkins Environment Variables
- `PROJECT_NAME`: Name of the project.
- `PROJECT_DESCRIPT`: Description of the project.
- `OWNER_NAME`: Name of the project owner.
- `CON_NAME`: Name of the Docker container.
- `IMAGE_NAME`: Name of the Docker image.

## Contributing
Please fork the repository and submit pull requests for any improvements or bug fixes.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

