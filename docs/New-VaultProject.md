---
external help file: Catesta-help.xml
Module Name: Catesta
online version: https://www.catesta.dev/en/latest/New-VaultProject/
schema: 2.0.0
---

# New-VaultProject

## SYNOPSIS

Scaffolds a PowerShell SecretManagement vault project for use with desired CICD platform for easy cross platform PowerShell development.

## SYNTAX

```powershell
New-VaultProject [-DestinationPath] <String> [[-VaultParameters] <Hashtable>] [-NoLogo] [-PassThru] [-Force]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Uses the Plaster framework to scaffold a PowerShell SecretManagement vault project that adheres to community best practices.
Based on selections made, generates the files and configuration required to integrate with a variety of CI/CD platforms,
including options for easy cross-platform verification on Windows, Linux, and MacOS.
InvokeBuild tasks will be created for validation, analysis, testing, and build automation.
Additional selections can generate other helpful files such as GitHub community files and VSCode project files.
If no VaultParameters are passed in, you will be prompted by Plaster for a decision on each template choice.
If you pass in a partial VaultParameters, you will be prompted by Plaster for any missing template decisions.
If you pass in a full VaultParameters set, Plaster will not prompt you for any template decisions.

## EXAMPLES

### EXAMPLE 1

```powershell
New-VaultProject -DestinationPath $outPutPath
```

Initiates Plaster template to scaffold a PowerShell SecretManagement vault project with customizable CI/CD integration options.
Choices made during scaffolding will result in a PowerShell project tailored to the chosen CI/CD platform, or a standard PowerShell SecretManagement vault project with no CI/CD integration.

### EXAMPLE 2

```powershell
New-VaultProject -DestinationPath $outPutPath -NoLogo
```

Initiates Plaster template to scaffold a PowerShell SecretManagement vault project with customizable CI/CD integration options.
Choices made during scaffolding will result in a PowerShell project tailored to the chosen CI/CD platform, or a standard PowerShell SecretManagement vault project with no CI/CD integration.
The Plaster logo will be suppressed and not shown.

### EXAMPLE 3

```powershell
New-VaultProject -DestinationPath $outPutPath -PassThru
```

Initiates Plaster template to scaffold a PowerShell SecretManagement vault project with customizable CI/CD integration options.
Choices made during scaffolding will result in a PowerShell project tailored to the chosen CI/CD platform, or a standard PowerShell SecretManagement vault project with no CI/CD integration.
An object will be returned containing details of the Plaster template deployment.

### EXAMPLE 4

```powershell
$vaultParameters = @{
    ModuleName       = 'SecretManagement.VaultName'
    Description      = 'My awesome vault is awesome'
    Version          = '0.0.1'
    FN               = 'user full name'
    CICD             = 'NONE'
    RepoType         = 'NONE'
    CodingStyle      = 'Stroustrup'
    Pester           = '5'
    NoLogo           = $true
}
New-VaultProject -VaultParameters $vaultParameters -DestinationPath $outPutPath
```

Scaffolds a basic PowerShell SecretManagement vault project with no additional extras.
You just get a basic PowerShell SecretManagement vault construct.

### EXAMPLE 5

```powershell
$vaultParameters = @{
    ModuleName     = 'SecretManagement.VaultName'
    Description    = 'My awesome vault is awesome'
    Version        = '0.0.1'
    FN             = 'user full name'
    CICD           = 'GITHUB'
    GitHubAOptions = 'windows', 'pwshcore', 'linux', 'macos'
    RepoType       = 'GITHUB'
    ReadtheDocs    = 'READTHEDOCS'
    RTDTheme       = 'READTHEDOCSTHEME'
    License        = 'MIT'
    Changelog      = 'CHANGELOG'
    COC            = 'CONDUCT'
    Contribute     = 'CONTRIBUTING'
    Security       = 'SECURITY'
    CodingStyle    = 'Stroustrup'
    Pester         = '5'
    S3Bucket       = 'PSGallery'
    NoLogo         = $true
}
New-VaultProject -VaultParameters $vaultParameters -DestinationPath $outPutPath
```

Scaffolds a PowerShell SecretManagement vault project for integration with GitHub Actions with the project code stored in GitHub.
A full set of GitHub project supporting files is provided.
The project is set up for integration with Read the Docs.

### EXAMPLE 6

```powershell
$vaultParameters = @{
    ModuleName  = 'SecretManagement.VaultName'
    Description = 'My awesome vault is awesome'
    Version     = '0.0.1'
    FN          = 'user full name'
    CICD        = 'CODEBUILD'
    AWSOptions  = 'ps', 'pwshcore', 'pwsh'
    RepoType    = 'GITHUB'
    ReadtheDocs = 'NONE'
    License     = 'MIT'
    Changelog   = 'CHANGELOG'
    COC         = 'CONDUCT'
    Contribute  = 'CONTRIBUTING'
    Security    = 'SECURITY'
    CodingStyle = 'Stroustrup'
    Pester      = '5'
    S3Bucket    = 'PSGallery'
    NoLogo      = $true
}
New-VaultProject -VaultParameters $vaultParameters -DestinationPath $outPutPath
```

Scaffolds a PowerShell SecretManagement vault project for integration with AWS CodeBuild with the project code stored in GitHub.
A full set of GitHub project supporting files is provided.

### EXAMPLE 7

```powershell
$vaultParameters = @{
    ModuleName   = 'SecretManagement.VaultName'
    Description  = 'My awesome vault is awesome'
    Version      = '0.0.1'
    FN           = 'user full name'
    CICD         = 'AZURE'
    AzureOptions = 'windows', 'pwshcore', 'linux', 'macos'
    RepoType     = 'GITHUB'
    ReadtheDocs  = 'NONE'
    License      = 'NONE'
    Changelog    = 'NONE'
    COC          = 'NONE'
    Contribute   = 'NONE'
    Security     = 'NONE'
    CodingStyle  = 'Stroustrup'
    Pester       = '5'
    NoLogo       = $true
}
New-VaultProject -VaultParameters $vaultParameters -DestinationPath $outPutPath
```

Scaffolds a PowerShell SecretManagement vault project for integration with Azure Pipelines with the project code stored in GitHub.
No repository supporting files are included.

### EXAMPLE 8

```powershell
$vaultParameters = @{
    ModuleName      = 'SecretManagement.VaultName'
    Description     = 'My awesome vault is awesome'
    Version         = '0.0.1'
    FN              = 'user full name'
    CICD            = 'APPVEYOR'
    AppveyorOptions = 'windows', 'pwshcore', 'linux', 'macos'
    RepoType        = 'GITHUB'
    ReadtheDocs     = 'NONE'
    License         = 'NONE'
    Changelog       = 'NONE'
    COC             = 'NONE'
    Contribute      = 'NONE'
    Security        = 'NONE'
    CodingStyle     = 'Stroustrup'
    Pester          = '5'
    PassThru        = $true
    NoLogo          = $true
}
New-VaultProject -VaultParameters $vaultParameters -DestinationPath $outPutPath
```

Scaffolds a PowerShell SecretManagement vault project for integration with Appveyor with the project code stored in GitHub.
No repository supporting files are included.

### EXAMPLE 9

```powershell
$vaultParameters = @{
    ModuleName  = 'SecretManagement.VaultName'
    Description = 'My awesome vault is awesome'
    Version     = '0.0.1'
    FN          = 'user full name'
    CICD        = 'BITBUCKET'
    RepoType    = 'BITBUCKET'
    ReadtheDocs = 'NONE'
    License     = 'NONE'
    Changelog   = 'CHANGELOG'
    COC         = 'CONDUCT'
    Contribute  = 'CONTRIBUTING'
    Security    = 'SECURITY'
    CodingStyle = 'Stroustrup'
    Pester      = '5'
    PassThru    = $true
    NoLogo      = $true
}
New-VaultProject -VaultParameters $vaultParameters -DestinationPath $outPutPath
```

Scaffolds a PowerShell SecretManagement vault project for integration with Bitbucket pipelines with the project code stored on Bitbucket.
A full set of repository supporting files are included.

### EXAMPLE 10

```powershell
$vaultParameters = @{
    ModuleName    = 'SecretManagement.VaultName'
    Description   = 'My awesome vault is awesome'
    Version       = '0.0.1'
    FN            = 'user full name'
    CICD          = 'GITLAB'
    GitLabOptions = 'windows', 'pwshcore', 'linux'
    RepoType      = 'GITLAB'
    ReadtheDocs   = 'READTHEDOCS'
    RTDTheme      = 'READTHEDOCSTHEME'
    License       = 'NONE'
    Changelog     = 'CHANGELOG'
    COC           = 'CONDUCT'
    Contribute    = 'CONTRIBUTING'
    Security      = 'SECURITY'
    CodingStyle   = 'Stroustrup'
    Pester        = '5'
    PassThru      = $true
    NoLogo        = $true
}
New-VaultProject -VaultParameters $vaultParameters -DestinationPath $outPutPath
```

Scaffolds a PowerShell SecretManagement vault project for integration with GitLab pipelines with the project code stored on GitLab.
A full set of repository supporting files are included.
The project is set up for integration with Read the Docs.

## PARAMETERS

### -DestinationPath

File path where PowerShell SecretManagement vault project will be created

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VaultParameters

Provide all Plaster decisions inside a Hashtable.
If any decision choice is not provided, Plaster will still prompt you for a decision.
See NOTES for additional limitations.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoLogo

Suppresses the display of the Plaster logo.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Returns an object containing details of Plaster template deployment.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force

Skip Confirmation

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm

Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutBuffer, -OutVariable, -PipelineVariable, -Verbose, -WarningAction, -WarningVariable, and -ProgressAction. 
For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### System.Management.Automation.PSCustomObject

## NOTES

Author: Jake Morrison - @jakemorrison - https://www.techthoughts.info/

## RELATED LINKS

[https://www.catesta.dev/en/latest/New-VaultProject/](https://www.catesta.dev/en/latest/New-VaultProject/)

[https://www.catesta.dev/en/latest/Catesta-Vault-Extension/](https://www.catesta.dev/en/latest/Catesta-Vault-Extension/)

[https://github.com/PowerShell/SecretManagement](https://github.com/PowerShell/SecretManagement)
