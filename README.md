# Commitlint PR Title Action

[![CI](https://github.com/ovsds/commitlint-pr-title-action/workflows/Check%20PR/badge.svg)](https://github.com/ovsds/commitlint-pr-title-action/actions?query=workflow%3A%22%22Check+PR%22%22)
[![GitHub Marketplace](https://img.shields.io/badge/Marketplace-Commitlint%20PR%20Title-blue.svg)](https://github.com/marketplace/actions/commitlint-pr-title)

Commitlint PR Title Action

## Usage

### Basic Example

```yaml
name: Check PR Title

on:
  pull_request:
    types:
      - opened
      - reopened
      - synchronize
      - edited

jobs:
  commitlint-pr-title:
    runs-on: ubuntu-latest

    steps:
      - name: Commitlint PR Title
        uses: ovsds/commitlint-pr-title-action@v1
```

### Example with custom configuration

```yaml
- name: Commitlint PR Title
  uses: ovsds/commitlint-pr-title-action@v1
  with:
    config_file: ./commitlint.config.js
```

### Action Inputs

| Name                           | Description                                                           | Default                                                              |
| ------------------------------ | --------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `pr_title`                     | PR title                                                              | `${{ github.event.pull_request.title }}`                             |
| `config_file`                  | Commitlint configuration file path                                    |                                                                      |
| `config`                       | Commitlint configuration plaintext, ignored if `config_file` provided | `module.exports = { extends: ["@commitlint/config-conventional"] };` |
| `node_modules`                 | Path to `node_modules` directory                                      |                                                                      |
| `node_version`                 | Node.js version, ignored if `node_modules` provided                   | `v20.15.1`                                                           |
| `commitlint_version`           | Commitlint version, ignored if `node_modules` provided                | `^19.5.0`                                                            |
| `additional_node_dependencies` | Additional node dependencies, ignored if node_modules is provided     | `@commitlint/config-conventional@^19.5.0`                            |

## Development

### Global dependencies

- [Taskfile](https://taskfile.dev/installation/)
- [nvm](https://github.com/nvm-sh/nvm?tab=readme-ov-file#install--update-script)
- [zizmor](https://woodruffw.github.io/zizmor/installation/) - used for GHA security scanning

### Taskfile commands

For all commands see [Taskfile](Taskfile.yaml) or `task --list-all`.

## License

[MIT](LICENSE)
