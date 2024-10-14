---
title: Install the Azure CLI on macOS | Microsoft Docs
description: Learn how to install and run the Azure CLI on macOS using the homebrew package manager. The Azure CLI has been tested on macOS versions 10.9 and later.
author: jiasli
ms.author: jiasli
manager: yonzhan
ms.date: 06/19/2023
ms.topic: concept-article
ms.service: azure-cli
ms.custom: devx-track-azurecli
keywords: Install azure cli, azure cli macos, macos cli, install azure cli macos
---

# Install Azure CLI on macOS

[!INCLUDE [current-version](includes/current-version.md)]

## Install with Homebrew

* [homebrew package manager](https://brew.sh)
  * [install homebrew](https://docs.brew.sh/Installation.html)
  * allows
    * installing
    * updating
    * uninstalling
* 👁️recommended one 👁
*
    ```bash
    brew update && brew install azure-cli 
    ```
  * `az --version`
    * check if the installation was suceed

### Troubleshooting

* next subsections display common errors -- through -- installation
  * otherwise -> [file an issue on GitHub](https://github.com/Azure/azure-cli/issues)

#### Completion isn't working

* TODO:
The Homebrew formula of Azure CLI installs a completion file named `az` in the Homebrew-managed completions directory (default location is `/usr/local/etc/bash_completion.d/`). To enable completion, follow Homebrew's instructions [here](https://docs.brew.sh/Shell-Completion).

For Zsh, add the following two lines to the bottom of your `.zshrc` file, then save and reload your Zsh profile.

```
autoload bashcompinit && bashcompinit
source $(brew --prefix)/etc/bash_completion.d/az
```

#### Unable to find Python or installed packages

There may be a minor version mismatch or other issue during homebrew installation. The CLI doesn't use a Python virtual environment, so it relies on finding
the installed Python version. A possible fix is to install and relink the `python@3.10` dependency from Homebrew.

```bash
brew update && brew install python@3.10 && brew upgrade python@3.10
brew link --overwrite python@3.10
```

#### CLI version 1.x is installed

If an out-of-date version was installed, it could be because of a stale homebrew cache. Follow the [update](#update) instructions.

#### Proxy blocks connection

You may be unable to get resources from Homebrew unless you have correctly configured it to
use your proxy. Follow the [Homebrew proxy configuration instructions](https://docs.brew.sh/Manpage#using-homebrew-behind-a-proxy).

> [!IMPORTANT]
> If you are behind a proxy, `HTTP_PROXY` and `HTTPS_PROXY` must be set to connect to Azure services with the CLI.
> If you are not using basic auth, it's recommended to export these variables in your `.bashrc` file.
> Always follow your business' security policies and the requirements of your system administrator.

In order to get the bottle resources from Homebrew, your proxy needs to allow HTTPS connections to
the following addresses:

* `https://formulae.brew.sh`
* `https://homebrew.bintray.com`

### Update

* new release / 3 weeks

[!INCLUDE [az-upgrade](includes/az-upgrade.md)]
*
    ```bash
    brew update && brew upgrade azure-cli
    ```

### Uninstall

[!INCLUDE [uninstall-boilerplate.md](includes/uninstall-boilerplate.md)]

* 

    ```bash
    brew uninstall azure-cli
    ```

## Remove data

* If you do NOT plan to reinstall Azure CLI -> remove its data

    ```bash
    rm -rf ~/.azure
    ```

## Other installation methods

* TODO:
If you can't use homebrew to install the Azure CLI in your environment, it's possible to use the manual instructions for Linux. This process isn't officially maintained to be compatible with macOS. Using a package manager such as Homebrew is always recommended. Only use the manual
installation method if you have no other option available.

For the manual installation instructions, see [Install Azure CLI on Linux manually](install-azure-cli-linux.md).

## Next Steps

* [Get started with the Azure CLI](get-started-with-azure-cli.md)
