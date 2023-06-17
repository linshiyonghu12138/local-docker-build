# local-docker-build
Conveniently build Docker images in GitHub Actions with the build and push process performed within your CI machine. This allows you to download dependencies and build your project beforehand, and in the Dockerfile, only copy the minimal packages required for your runtime into the container. This approach helps reduce the size of the Docker image.
