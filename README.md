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

### e2e_test

#### Parameters

| name | default | required |
|-|-|-|
|`OIDC_CLIENT_ID` (secret)||✅|
|`OIDC_CLIENT_SECRET` (secret)||✅|
|`environment`||✅|
|`working-directory`|`.`|❌|
|`backend-directory`|`.`|❌|

#### Example

```yml
job_name:
    uses: game-ai-platform-team/workflows/.github/workflows/e2e_test.yml@main
    with:
        working-directory: ./frontend
        environment: staging
        backend-directory: ./backend
    secrets:
        OIDC_CLIENT_ID: ${{ secrets.OIDC_CLIENT_ID }}
        OIDC_CLIENT_SECRET: ${{ secrets.OIDC_CLIENT_SECRET }}
```
