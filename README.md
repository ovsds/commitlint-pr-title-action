# Commitlint PR Title Action

[![CI](https://github.com/ovsds/commitlint-pr-title-action/workflows/Check%20PR/badge.svg)](https://github.com/ovsds/commitlint-pr-title-action/actions?query=workflow%3A%22%22Check+PR%22%22)
[![GitHub Marketplace](https://img.shields.io/badge/Marketplace-Commitlint%20PR%20Title-blue.svg)](https://github.com/marketplace/actions/commitlint-pr-title)

Commitlint PR Title Action

## Usage

### Example

```yaml
jobs:
  commitlint-pr-title:
    permissions:
      contents: read

    steps:
      - name: Commitlint PR Title
        id: commitlint-pr-title
        uses: ovsds/commitlint-pr-title-action@v1
```

### Action Inputs

| Name          | Description  | Default |
| ------------- | ------------ | ------- |
| `placeholder` | Placeholder. |         |

### Action Outputs

| Name          | Description  |
| ------------- | ------------ |
| `placeholder` | Placeholder. |

## Development

### Global dependencies

- [Taskfile](https://taskfile.dev/installation/)
- [nvm](https://github.com/nvm-sh/nvm?tab=readme-ov-file#install--update-script)

### Taskfile commands

For all commands see [Taskfile](Taskfile.yaml) or `task --list-all`.

## License

[MIT](LICENSE)
