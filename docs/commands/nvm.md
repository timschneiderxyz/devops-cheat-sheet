# Commands - nvm

Update nvm:

```sh
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | sh
```

List Node versions:

```sh
nvm ls # Show the Node versions installed.
nvm ls-remote # Shows all the Node versions available.
```

Managing Node:

```sh
nvm install <version> # Install the specified Node version.
nvm install --reinstall-packages-from=<previous_version> <version> # Install the specified Node version and migrate packages from a previous version.
nvm uninstall <version> # Uninstall the specified Node version.
nvm alias default <version> # Set the default Node version.
nvm use <version> # Switch to the specified Node version.
```

Get the latest supported npm version on the current Node version:

```sh
nvm install-latest-npm
```
