# tyk-cli

Tyk CLI utility.

[![Build Status](https://travis-ci.org/TykTechnologies/tyk-cli.svg?branch=master)](https://travis-ci.org/TykTechnologies/tyk-cli)

## Install

```
go get github.com/TykTechnologies/tyk-cli
go install github.com/TykTechnologies/tyk-cli
```

## Available modules

### Bundle

This module provides useful commands for working with custom middleware bundles. The most basic command is `build`:

Assuming you're on a directory that contains your required bundle files and a **bundle manifest**, you could run:

```
tyk-cli bundle build -output bundle-latest.zip
```

If no `-output` flag is present, the bundle will be stored as `bundle.zip` in the current working directory.

The bundle will contain a `manifest.json` with the computed checksum and signature.

By default, the bundles are signed, if no private key is specified, the program will prompt for a confirmation. If you need to force this behavior you may use the `-y` flag:

```
tyk-cli bundle build -output bundle-latest.zip -y
```

If you follow the standard behavior and need to sign your bundles, provide the path to your private key using the `-key` flag:

```
tyk-cli bundle build -output bundle-latest.zip -key mykey.pem
```

## Docs

For more information about rich plugins, check the documentation [here](https://tyk.io/tyk-documentation/customise-tyk/plugins/).

## License

Tyk is released under the MPL v2.0 please see the [LICENSE.md](LICENSE.md) file for a full version of the license.
