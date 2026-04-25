# ✅ Experiment 7 – GitHub Actions with Docker Buildx

## Aim
To build and push Docker image using Buildx.

## Where to Do It
Use **GitHub Repository**

## Create File

.github/workflows/buildx.yml

## YAML Code

```yaml
name: Buildx Pipeline

on:
  push:
    branches: [main]

jobs:
  docker:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - uses: docker/setup-buildx-action@v3
```

## Push File

```bash
git add .
git commit -m "Buildx Added"
git push
```

## Expected Output

Docker image pushed automatically.
