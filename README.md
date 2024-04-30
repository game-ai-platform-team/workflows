# Workflows

Repository for GitHub Actions workflow files

## Usage

### ci_python

#### Parameters

| name | default | required |
|-|-|-|
|`CODECOV_TOKEN` (secret)||✅|
|`environment`||❌|
|`working-directory`|`.`|❌|

#### Example

```yml
job_name:
    permissions:
      contents: write

    uses: game-ai-platform-team/workflows/.github/workflows/ci_python.yml@main
    with:
      working-directory: .
      environment: staging
    secrets:
      CODECOV_TOKEN: ${{ secrets.CODECOV_TOKEN }}
```

### ci_node

#### Parameters

| name | default | required |
|-|-|-|
|`CODECOV_TOKEN` (secret)||✅|
|`working-directory`|`.`|❌|

#### Example

```yml
job_name:
    permissions:
        contents: write

    uses: game-ai-platform-team/workflows/.github/workflows/ci_node.yml@main
    with:
        working-directory: .
    secrets:
        CODECOV_TOKEN: ${{ secrets.CODECOV_TOKEN }}
```

### pypi_deploy

#### Parameters

| name | default | required |
|-|-|-|
|`PYPI_TOKEN` (secret)||✅|

#### Example

```yml
name: Deploy
on:
  workflow_dispatch:

jobs:
  deploy:
    uses: game-ai-platform-team/workflows/.github/workflows/pypi_deploy.yml@main

    secrets:
      PYPI_TOKEN: ${{ secrets.PYPI_TOKEN }}
```
