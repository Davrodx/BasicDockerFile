# BasicDockerFile
Dockerized Node.js service with a public health route and a Basic Auth–protected /secret endpoint that returns a value from environment variables. Includes a production-ready Dockerfile that excludes .env, plus a GitHub Actions pipeline that builds the image, pushes it to GHCR, and deploys it to an Ubuntu VM over SSH with GH secrets.
