# Project Setup Guide

This guide explains how to set up the new laravel project Dockerfile without changing any source code.

## Prerequisites

Before proceeding with the setup, ensure you have the following installed:

- Docker
- Docker Compose

## Steps to Set Up the Project

### 1. Clone the Repository

If you haven't already, clone the project repository:

```bash
git clone <repository_url>
cd <project_directory>
```

### 2. Docker Setup

In this project, we are using a custom Dockerfile to set up the PHP environment. Follow these steps to set up the Docker container:

### 3. Build the Docker Image

After configuring the `Dockerfile` and Composer files, build the Docker container using the following command:

```bash
docker-compose build --no-cache
```

This will rebuild the Docker image, ensuring all required packages and configurations are applied.

### 4. Start the Docker Container

Once the build is complete, start the Docker container:

```bash
docker-compose up -d
```

This command will start the container in detached mode.

### 5. Verify the Setup

To check if everything is working correctly, access the container logs:

```bash
docker-compose logs -f
```

Look for any errors. If there are no issues, your setup should be complete.

---

### Conclusion

Following these steps, you should have your Docker environment set up with the required dependencies without needing to modify the source code. If you encounter any issues, refer to the troubleshooting section above or reach out to the support team for assistance.

### Happy coding :)...