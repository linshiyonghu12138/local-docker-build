# Local Docker Build
Conveniently build Docker images in GitHub Actions with the build and push process performed within your CI machine. This allows you to download dependencies and build your project beforehand, and in the Dockerfile, only copy the minimal packages required for your runtime into the container. This approach helps reduce the size of the Docker image.

### Installation
Copy and paste the following snippet into your .yml file.
 ```yaml
  - name: Docker Build And Push
    uses: ./
    with:
      # Name of the Docker image
      image:
      # Tags override for Docker image
      tags: # optional
      # Target Docker registry
      registry: # optional, default is docker hub (docker.io)
      # Docker repository
      repository: # optional, default is you registry username
      # Location of Dockerfile, if not Dockerfile in root directory
      dockerfile: # optional, default is './Dockerfile'
      # Directory to run `docker build` from, if not project root
      directory: # optional
      # Docker build arguments passed via --build-arg
      buildArgs: # optional
      # Docker build labels passed via --label
      labels: # optional
      # Docker build target passed via --target
      target: # optional
      # Docker build platform passed via --platform
      platform: # optional
      # Docker build ssh options passed via --ssh
      ssh: # optional
      # Docker registry username
      username: # optional
      # Docker registry password
      password: # optional
      # Adds latest tag to auto-generated GitOps tag
      addLatest: # optional, default is false
      # Suffixes a build timestamp to the branch-based Docker tag
      addTimestamp: # optional, default is false
      # Flag for disabling the login & push steps, set to true by default
      pushImage: # optional, default is true
      # When using timestamp as tag, set timestamp timeZone (linux timeZone)
      timeZone: # optional, default is UTC
```