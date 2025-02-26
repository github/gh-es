# GitHub Enterprise Server CLI

This is the management tool for GitHub Enterprise Server (GHES) on the command line.

## Installation

`gh es` is available for installation as a `gh` CLI extension, and as a downloadable binary from the [releases page](https://github.com/github/gh-es/releases/latest).

In order to use it as a [CLI extension](https://cli.github.com/manual/gh_extension_install), you must have the GitHub CLI [installed](https://github.com/cli/cli/#installation).

To install the latest version, use:

```bash
gh extension install github.com/github/gh-es
```

Please make sure to install the correct version of the CLI extension which matches the release version (e.g. `3.16.0`) of your GHES installation, by pinning to the latest patch for the corresponding release series:

```bash
gh extension install github.com/github/gh-es --pin v3.16.0
```

## Supported versions

The following versions of GHES are supported by this CLI. Please refer to the [USAGE](./USAGE.md) for more information on how to use the CLI commands of each release.

* [3.12](https://github.com/github/gh-es/blob/3.12/README.md)
* [3.13](https://github.com/github/gh-es/blob/3.13/README.md)
* [3.14](https://github.com/github/gh-es/blob/3.14/README.md)
* [3.15](https://github.com/github/gh-es/blob/3.15/README.md)
* [3.16](https://github.com/github/gh-es/blob/main/README.md)

## Usage

For more information on how to use the CLI and its commands, please see the [USAGE](./USAGE.md) documentation.

## License

This project is licensed under the terms of the MIT open source license. Please refer to [LICENSE](./LICENSE.md) for the full terms.

## Support

See [SUPPORT](./SUPPORT.md).

## Contributing

See [CONTRIBUTING](./CONTRIBUTING.md).
