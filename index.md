---
layout: default
title: Home
nav_order: 1
---

# AppVentiX PowerShell Module

Welcome to the documentation for the **AppVentiX** PowerShell Module. This module provides tools for managing App-V packages and enabling seamless application publishing.

## Overview

AppVentiX is a comprehensive solution for managing packages like App-V and MSIX and much more:

- Creating publishing tasks for seamless application delivery
- Managing machine groups and content shares
- Configuring deployment and user configurations

## Getting Started

### Prerequisites

- Windows PowerShell 5.1 or later
- Valid AppVentiX license

### Installation

```powershell
# Installing the latest module from the PowerShell Gallery:
Install-Module -Name AppVentiX -Force

# Import the module
Import-Module AppVentiX
```

### Configuration


Before using the module, a connection must be made to the config share.
When the AppVentiX Powershell module is installed on the same machine as the AppVentiX Central management Console it will automatically detect the config share when configured correctly.
You can also configure the share manually if the detection does not succeed or is being run from a diffrent machine. To configure your AppVentiX environment:

```powershell
# Set the configuration share path
Set-AppVentiXConfigShare -Path "\\fileserver.domain.com\config$"

# If credentials are required to connect to the Configuration Share, you can provide these

$Credential = Get-Credential -Message "Provide a username and password to connect to the Configuration Share"
Set-AppVentiXConfigShare -Path "\\fileserver.domain.com\config$" -Credential $Credential

# To verify your license
Test-AppVentiXIsLicensed
```

## Available Commands

### Migration Commands

These commands help you migrate from App-V Management Server to AppVentiX:

| Command | Description |
|---------|-------------|
| [Import-AppVManagementPackage](commands/Import-AppVManagementPackage.html) | Imports App-V packages from the Management Database |
| [Import-AppVManagementConnectionGroup](commands/Import-AppVManagementConnectionGroup.html) | Imports Connection Groups from the Management Database |

## HowTo Guides

Step-by-step guides for common tasks:

| Guide | Description |
|-------|-------------|
| [Import packages from App-V Management Database](howto/Import-packages-from-AppV-Management-Database.html) | Complete guide for migrating App-V packages |

## Support

For questions, issues, or feature requests, please contact [AppVentiX Support](https://support.appventix.com/)
---

*Copyright (c) AppVentiX*
