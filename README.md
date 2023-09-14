# GitHub Enterprise Server CLI

This is the management tool for GitHub Enterprise Server (GHES) on the command line.

## Installation

`gh es` is available for installation as a `gh` CLI extension, and as a downloadable binary from the [releases page](https://github.com/github/gh-es/releases/latest).

In order to use it as a [CLI extension](https://cli.github.com/manual/gh_extension_install), you must have the GitHub CLI [installed](https://github.com/cli/cli/#installation).

To install the latest version, use:

```bash
gh extension install github.com/github/gh-es
```

Please make sure to install the correct version of the CLI extension which matches the version of your GHES installation, by pinning to the corresponding release tag:

```bash
gh extension install github.com/github/gh-es --pin v3.11.0
```

## Usage

For more information on how to use the CLI and it's commands, please see the [usage](./USAGE.md) documentation.
