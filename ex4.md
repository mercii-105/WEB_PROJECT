# ✅ Experiment 4 – CI Pipeline using GitHub Actions

## Aim
To automatically build Docker image using GitHub Actions.

## Where to Do It
Use **GitHub Repository**

## Create File

.github/workflows/docker-publish.yml

## YAML Code

```yaml
name: CI Pipeline

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - run: docker build -t myapp .
```

## Push File

```bash
git add .
git commit -m "CI Added"
git push
```

## Expected Output

Green tick in GitHub Actions.
