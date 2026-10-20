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

| Name                           | Description                                                                                     | Default                                                              |
| ------------------------------ | ----------------------------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| `pr_title`                     | PR title                                                                                        | `${{ github.event.pull_request.title }}`                             |
| `config_file`                  | Commitlint configuration file path                                                              |                                                                      |
| `config`                       | Commitlint configuration plaintext, ignored if `config_file` provided                           | `module.exports = { extends: ["@commitlint/config-conventional"] };` |
| `node_modules`                 | Path to `node_modules` directory                                                                |                                                                      |
| `node_version`                 | Node.js version, ignored if `node_modules` provided; commitlint 21 needs Node.js 22.12 or later | `v24.22.0`                                                           |
| `commitlint_version`           | Commitlint version, ignored if `node_modules` provided                                          | `^21.2.4`                                                            |
| `additional_node_dependencies` | Additional node dependencies, ignored if node_modules is provided                               | `@commitlint/config-conventional@^21.2.4`                            |

### Action Outputs

| Name                   | Description          |
| ---------------------- | -------------------- |
| `commitlint_stdout`    | Commitlint stdout    |
| `commitlint_stderr`    | Commitlint stderr    |
| `commitlint_exit_code` | Commitlint exit code |

## Development

### Global dependencies

- [mise](https://mise.jdx.dev/installing-mise.html), activated in the shell (`eval "$(mise activate zsh)"`)

All other tools are pinned in [mise.toml](mise.toml).

### mise tasks

For all commands see [mise.toml](mise.toml) or `mise tasks ls`.

## License

[MIT](LICENSE)
