---
title: Learn about Azure CLI environments, terms, and compare the Azure CLI to Azure PowerShell | Microsoft Docs
description: Learn the environments you can use to execute Azure CLI commands, Azure CLI terms, how the Azure CLI compares to Azure PowerShell.
ms.date: 12/04/2023
ms.topic: concept-article
ms.service: azure-cli
ms.custom: devx-track-azurecli, devx-track-azurepowershell
keywords: azure, az account, az group, az config, az init, configuration
---
# Begin your Azure CLI journey

* goal
  * know the Azure CLI
    * [here](get-started-tutorial-0-before-you-begin.md)
    * vs PowerShell _tools_
    * Azure CLI command components
  * TODO:
> * 2 - [Prepare your environment for the Azure CLI](./get-started-tutorial-1-prepare-environment.md)
>   * Compare Bash and PowerShell _environments_.
>   * Set environment variables.
>   * Add a random ID to an Azure resource name.
>
> * 3 - [Compare Azure CLI syntax differences in Bash, PowerShell and Cmd](./get-started-tutorial-2-environment-syntax.md)
>   * Understand differences in line continuation and variable usage.
>   * Compare quoting differences and escape characters between environments.
>   * Work with dates.
>
> * 4 - [Populate variables for use in scripts](./get-started-tutorial-3-use-variables.md)
>   * Get (query) Azure resource properties.
>   * Store the results of a command in a variable, such as a password or secret.
>   * Store the contents of a JSON file in a variable, such as development or production settings.
>
> * 5 - [Delete Azure resources at scale using a script](./get-started-tutorial-4-delete-resources.md)
>   * Delete Azure resources using a FOR..EACH loop.

## What is the Azure CLI?

* [what is Azure CLI](./what-is-azure-cli.md)

## What shell environment should I use?

* alternatives
  * Windows PowerShell,
  * PowerShell,
  * Cmd,
  * Bash
* determines 
  * tools / you can use
  * changes your CL experience
* examples files here -- are written for --
  * Bash,
  * PowerShell
  * Cmd

|Shell environment | Can I use Azure CLI? | Can I use Azure PowerShell?|
|-|-|-|
| CMD | Yes ||
| Bash | Yes ||
| Windows PowerShell | Yes | Yes |
| PowerShell | Yes | Yes |

* Azure Cloud Shell
  * == hosted shell environment / runs | Ubuntu container
    * shell environments provided
      * Bash / Azure CLI preinstalled
      * PowerShell / Azure PowerShell preinstalled

## Azure CLI vs Azure PowerShell?


| Compare | Azure CLI | Azure PowerShell |
|-|-|-|
|What is it?|Cross-platform **_command-line interface_** | Cross-platform **_PowerShell module_** == CL tool
|Built on | Python | PowerShell
|Install on| Windows, macOS, Linux | Windows, macOS, Linux
|Run in|Bash shell, PowerShell 5 or 7, Windows Cmd.exe, Azure Cloud Shell, Docker container, and other Unix shells.| Windows PowerShell, PowerShell, Azure Cloud Shell, Docker container
|Terms| Reference groups, reference subgroups and reference commands | Modules, cmdlets and aliases
|Syntax example | [az storage account create](/cli/azure/storage/account#az-storage-account-create) | [New-AzStorageAccount](/powershell/module/az.storage/new-azstorageaccount) |
|Learn more | [What is Azure CLI?](./what-is-azure-cli.md) | [What is Azure PowerShell?](/powershell/azure/what-is-azure-powershell)
|Release notes| [Azure CLI release notes](./release-notes-azure-cli.md) | [Azure PowerShell release notes](/powershell/azure/release-notes-azureps)

## Azure CLI command components

* types of Azure CLI reference commands (ALL are one of this)
  * **Core** components
    * == primary Azure CLI service /
      * ship from Microsoft | [release schedule](./release-notes-azure-cli.md)
  * **[Extensions](./azure-cli-extensions-overview.md)**
    * != part of the core Azure CLI, BUT they run as CLI commands
    * allows
      * gaining access to
        * experimental commands
        * prerelease commands
      * writing your own CLI interfaces
    * first time you use -> you're prompted to install an extension
* Azure CLI syntax
  * has four parts
    * `group`
    * `subgroups`
    * `command`
    * `parameters`
  * _Example:_ [az storage account local-user create](/cli/azure/storage/account/local-user#az-storage-account-local-user-create)

    | Term | Example |
    |-|-|
    | Reference `group` | az `storage`
    | Space-delimited reference `subgroups` | az storage `account` `local-user`
    | Reference `command` | az storage account local-user `create`
    | Reference command `parameters` | az storage account local-user create `--name`, `--account-name`, `--resource-group`

## Get more details


| Subject | Learn more |
|-|-|
| Environments | [Choose the right Azure command-line tool](./choose-the-right-azure-command-line-tool.md)
| Terms | [Azure CLI terms and status](reference-types-and-status.md) |
| Extensions | [Use and manage extensions with the Azure CLI](./azure-cli-extensions-overview.md)

## Next Step

> [!div class="nextstepaction"]
> [Prepare your environment for the Azure CLI](./get-started-tutorial-1-prepare-environment.md)
