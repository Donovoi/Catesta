# Catesta

[![Minimum Supported PowerShell Version](https://img.shields.io/badge/PowerShell-5.1+-purple.svg)](https://github.com/PowerShell/PowerShell) [![PowerShell Gallery][psgallery-img]][psgallery-site] ![Cross Platform](https://img.shields.io/badge/platform-windows%20%7C%20macos%20%7C%20linux-lightgrey) [![License][license-badge]](LICENSE) [![Documentation Status](https://readthedocs.org/projects/catesta/badge/?version=latest)](https://catesta.readthedocs.io/en/latest/?badge=latest)

[psgallery-img]:   https://img.shields.io/powershellgallery/dt/Catesta?label=Powershell%20Gallery&logo=powershell
[psgallery-site]:  https://www.powershellgallery.com/packages/Catesta
[license-badge]:   https://img.shields.io/github/license/techthoughts2/Catesta

<p align="center">
    <img src="./docs/assets/Catesta.PNG" alt="Catesta Logo" >
</p>

Branch | Windows - PowerShell | Windows - pwsh | Linux | MacOS
--- | --- | --- | --- | --- |
main | ![Build Status Windows PowerShell Main](https://github.com/techthoughts2/Catesta/workflows/Catesta-Windows-PowerShell/badge.svg?branch=main) | ![Build Status Windows pwsh Main](https://github.com/techthoughts2/Catesta/workflows/Catesta-Windows-pwsh/badge.svg?branch=main) | ![Build Status Linux Main](https://github.com/techthoughts2/Catesta/workflows/Catesta-Linux/badge.svg?branch=main) | ![Build Status MacOS Main](https://github.com/techthoughts2/Catesta/workflows/Catesta-MacOS/badge.svg?branch=main)
Enhancements | ![Build Status Windows PowerShell Enhancements](https://github.com/techthoughts2/Catesta/workflows/Catesta-Windows-PowerShell/badge.svg?branch=Enhancements) | ![Build Status Windows pwsh Enhancements](https://github.com/techthoughts2/Catesta/workflows/Catesta-Windows-pwsh/badge.svg?branch=Enhancements) | ![Build Status Linux Enhancements](https://github.com/techthoughts2/Catesta/workflows/Catesta-Linux/badge.svg?branch=Enhancements) | ![Build Status MacOS Enhancements](https://github.com/techthoughts2/Catesta/workflows/Catesta-MacOS/badge.svg?branch=Enhancements)

## Synopsis

Catesta is a PowerShell module project generator. It uses templates to rapidly scaffold test and build integration for a variety of CI/CD platforms.

## Description

Catesta enables you to quickly scaffold a [PowerShell module](https://docs.microsoft.com/powershell/scripting/developer/module/how-to-write-a-powershell-script-module?view=powershell-7) or [Vault extension](https://github.com/PowerShell/SecretManagement) project with proper formatting, test + build automation, CI/CD integration, with just one line of code.

* Catesta scaffolds an empty PowerShell/Vault extension module project that adheres to PowerShell community guidelines.
* It generates a few [Pester](https://github.com/pester/Pester) tests to get you started.
* It makes a [build file](https://github.com/nightroman/Invoke-Build) that analyzes your code for best practices and styling, runs Pester tests, creates PowerShell help, and combines your functions together to build your project for publication.
* It will create resources you need to trigger CI/CD builds for your module.
* When you commit your code to your chosen repository, the build(s) will run, and you can view the results.

[Catesta](docs/Catesta.md) provides the following functions:

* [New-PowerShellProject](docs/New-PowerShellProject.md)
* [New-VaultProject](docs/New-VaultProject.md)

## Why

Simplify the process of structuring your module so that you can focus on building a great PowerShell module instead of the layout and build requirements.

## Documentation

To learn more about Catesta go to the complete documentation.

## Installation

```powershell
# Install Catesta from the PowerShell Gallery
Install-Module -Name Catesta -Repository PSGallery -Scope CurrentUser
```

## Quick start

### PowerShell Module

```powershell
# Scaffolds a PowerShell module project for integration with AWS CodeBuild.
New-PowerShellProject -CICDChoice 'AWS' -DestinationPath C:\path\AWSProject

# Scaffolds a PowerShell module project for integration with GitHub Actions Workflows.
New-PowerShellProject -CICDChoice 'GitHubActions' -DestinationPath C:\path\GitHubActions

# Scaffolds a PowerShell module project for integration with Azure DevOps Pipelines.
New-PowerShellProject -CICDChoice 'Azure' -DestinationPath C:\path\AzurePipeline

# Scaffolds a PowerShell module project for integration with AppVeyor Projects.
New-PowerShellProject -CICDChoice 'AppVeyor' -DestinationPath C:\path\AppVeyor

# Scaffolds a basic PowerShell module project with no additional extras. You just get a basic PowerShell module construct.
New-PowerShellProject -CICDChoice 'ModuleOnly' -DestinationPath C:\path\ModuleOnly
```

### SecretManagement Vault Extension Module

```powershell
# Scaffolds a PowerShell SecretManagement vault module project for integration with AWS CodeBuild.
New-VaultProject -CICDChoice 'AWS' -DestinationPath C:\path\AWSProject

# Scaffolds a PowerShell SecretManagement vault module project for integration with GitHub Actions Workflows.
New-VaultProject -CICDChoice 'GitHubActions' -DestinationPath C:\path\GitHubActions

# Scaffolds a PowerShell SecretManagement vault module project for integration with Azure DevOps Pipelines.
New-VaultProject -CICDChoice 'Azure' -DestinationPath C:\path\AzurePipeline

# Scaffolds a PowerShell SecretManagement vault module project for integration with AppVeyor Projects.
New-VaultProject -CICDChoice 'AppVeyor' -DestinationPath C:\path\AppVeyor

# Scaffolds a basic PowerShell SecretManagement vault module project with no additional extras. You just get a basic module construct.
New-VaultProject -CICDChoice 'ModuleOnly' -DestinationPath C:\path\ModuleOnly
```

## Author

[Jake Morrison](https://twitter.com/JakeMorrison) - [https://www.techthoughts.info/](https://www.techthoughts.info/)

## Contributors

* [Andrew Pearce](https://twitter.com/austoonz)
* [Dave Kaylor](https://twitter.com/KaylorDave)

## Notes

To learn more about Catesta go to the complete documentation.

Additional Catesta documentation that covers PowerShell Vault Extension module projects more in depth:

* [Catesta - Vault Extension](docs/Catesta-Vault-Extension.md)

## Changelog

Reference the [Changelog](.github/CHANGELOG.md)
