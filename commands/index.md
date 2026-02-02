---
layout: default
title: Commands
nav_order: 2
---

# Command Reference

This section contains detailed documentation for all AppVentiX PowerShell commands.

## Migration Commands

Commands for migrating from App-V Management Server to AppVentiX:

| Command | Description |
|---------|-------------|
| [Import-AppVManagementPackage](Import-AppVManagementPackage.html) | Imports App-V packages from the Management Database to AppVentiX |
| [Import-AppVManagementConnectionGroup](Import-AppVManagementConnectionGroup.html) | Imports Connection Groups from the Management Database to AppVentiX |

## Usage Notes

### SQL Server Authentication

All migration commands support two authentication methods:

1. **Windows Integrated Authentication** (default): Uses the current Windows credentials
2. **SQL Server Authentication**: Uses a PSCredential object passed to the `-SQLCredential` parameter

```powershell
# Windows Integrated Authentication
Import-AppVManagementPackage -SQLServer "sql01.domain.local"

# SQL Server Authentication
$cred = Get-Credential
Import-AppVManagementPackage -SQLServer "sql01.domain.local" -SQLCredential $cred
```

### GUI Mode

Both import commands support a `-GUI` switch that displays a graphical selection dialog, allowing you to choose which items to import:

```powershell
Import-AppVManagementPackage -SQLServer "sql01" -GUI
```

### Machine Group Matching

Use the `-MatchPackageWithMachineGroup` or `-MatchConnectionGroupWithMachineGroup` switch to automatically assign packages to the appropriate machine groups based on their content share location.
