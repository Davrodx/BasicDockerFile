```md
# Basic Dockerfile — Hello, Captain!

Project URL: https://roadmap.sh/projects/basic-dockerfile

This repository contains a minimal `Dockerfile` that builds a Docker image which prints:

```

Hello, Captain!

```

…and then exits.

## Requirements (per project)

- `Dockerfile` is named **Dockerfile**
- `Dockerfile` is in the **root** directory
- Base image is **alpine:latest**
- Dockerfile uses a **single instruction** to print `Hello, Captain!` before exiting

## Project Structure

```

.
├─ Dockerfile
└─ README.md

````

## Dockerfile

```dockerfile
FROM alpine:latest
CMD ["sh", "-c", "echo \"Hello, Captain!\""]
````

## Run Locally

### Build

```bash
docker build -t hello-captain .
```

### Run

```bash
docker run --rm hello-captain
```

Expected output:

```text
Hello, Captain!
```

## Run in CI (Azure DevOps example)

If your pipeline only **builds** the image, you will not see the printed message because `docker build` does not execute `CMD`.
To see the output, add a step that **runs** the container:

```yaml
- script: |
    docker build -t hello-captain .
    docker run --rm hello-captain
  displayName: Build and run image
```

Then check the pipeline run logs for the `Build and run image` step.

```
<img width="1613" height="829" alt="image" src="https://github.com/user-attachments/assets/8b3b2550-5cb0-4322-9833-f3046d181569" />

```
