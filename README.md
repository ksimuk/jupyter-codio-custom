# jupyter-codio-custom

This repository contains a custom Docker image for Jupyter based on the Codio Jupyter standard image, with additional Python packages installed.

## Docker Image

- **Base image:** `public.ecr.aws/o0g3m8o6/codio/codio-jupyter:standard-latest`
- **Additional packages:**
	- `httpie`

## Building and Publishing

A GitHub Actions workflow is provided to build and publish the Docker image to GitHub Container Registry (GHCR) on every push to the `master` branch or via manual dispatch.

### Workflow file
- Location: `.github/workflows/docker-publish.yml`

### How it works
- Builds the Docker image from the repository root using the included `Dockerfile`.
- Tags the image as `ghcr.io/<OWNER>/<REPO>:<TAG>` (default tag is `latest`).
- Pushes the image to GitHub Packages (GHCR).

### Manual Dispatch
You can manually trigger the workflow from the GitHub Actions tab and specify a custom image tag.

## Usage

To pull and run the image:

```sh
docker pull ghcr.io/<OWNER>/<REPO>:latest
docker run -it ghcr.io/<OWNER>/<REPO>:latest
```
Replace `<OWNER>` and `<REPO>` with your GitHub username/organization and repository name.

## Customization
- Edit the `Dockerfile` to add or remove packages as needed.

## License
MIT