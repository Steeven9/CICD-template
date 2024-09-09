# CICD-template

![Test workflow](https://github.com/steeven9/CICD-template/actions/workflows/test.yml/badge.svg)

Shared template for GitHub Actions

## Usage

Just add this to `.github/workflows/your-workflow.yml`:

```yaml
name: your-workflow

on:
  push:
    branches: [main]

jobs:
  build-and-push:
    uses: steeven9/CICD-template/.github/workflows/docker-build.yml@main
    with:
      image-name: some-org/some-image # adapt to yours
      push: true
    secrets:
      DOCKERHUB_USERNAME: ${{ secrets.DOCKERHUB_USERNAME }}
      DOCKERHUB_TOKEN: ${{ secrets.DOCKERHUB_TOKEN }}
```

## Resources

### Actions used

<https://github.com/docker/login-action>

<https://github.com/docker/build-push-action>

### Documentation

<https://docs.github.com/en/actions/sharing-automations/reusing-workflows#creating-a-reusable-workflow>
