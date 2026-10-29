# devops-a2-fa23-bai-059

A small personal web page (plain HTML and CSS) used for DevOps Assignment 2.
It is kept in Git, packaged in a Docker image, and built and pushed to Docker Hub by GitHub Actions.

## Files

- `index.html`, `style.css`: the web page
- `Dockerfile`: nginx image that serves the page
- `.github/workflows/ci.yml`: checks the page, builds the image, pushes `latest` from main

## Run locally

```bash
docker build -t devops-a2 .
docker run -d -p 8080:80 --name page devops-a2
```

Open http://localhost:8080

## CI

On every push to `main` and every pull request, the workflow checks the page and builds the image.
The image is pushed to Docker Hub as `latest` only when the run is on `main`.
Webhook test
