# Setup Rokit GitHub Action

A custom GitHub Action to set up and use [Rokit](https://github.com/rojo-rbx/rokit), a tool for automating workflows and tool management in Roblox projects.

## Features

- Downloads and installs Rokit for your project.
- Sets up environment variables for easy usage.
- Optionally enables caching for faster builds.
- Configurable to match your project directory and version requirements.

## Inputs

| Name     | Description                                    | Required | Default              |
|----------|------------------------------------------------|----------|----------------------|
| `version`| `Rokit` version (e.g., `1.0.0`).               | No       | Latest release       |
| `path`   | Path to the `rokit.toml` directory.            | No       | `.` (current dir)    |
| `cache`  | Whether to enable caching of Rokit binaries.   | No       | `false`              |
| `token`  | GitHub token for accessing private releases.   | No       | `${{ github.token }}`|

## Example usage

Add the following step to your workflow:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Rokit
        uses: GGshor/setup-rokit@0.0.1
        with:
          version: 1.0.0
