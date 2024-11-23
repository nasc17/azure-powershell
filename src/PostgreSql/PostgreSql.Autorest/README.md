<!-- region Generated -->
# Az.PostgreSql
This directory contains the PowerShell module for the PostgreSql service.

---
## Info
- Modifiable: yes
- Generated: all
- Committed: yes
- Packaged: yes

---
## Detail
This module was primarily generated via [AutoRest](https://github.com/Azure/autorest) using the [PowerShell](https://github.com/Azure/autorest.powershell) extension.

## Module Requirements
- [Az.Accounts module](https://www.powershellgallery.com/packages/Az.Accounts/), version 2.7.5 or greater

## Authentication
AutoRest does not generate authentication code for the module. Authentication is handled via Az.Accounts by altering the HTTP payload before it is sent.

## Development
For information on how to develop for `Az.PostgreSql`, see [how-to.md](how-to.md).
<!-- endregion -->

---
## Generation Requirements
Use of the beta version of `autorest.powershell` generator requires the following:
- [NodeJS LTS](https://nodejs.org) (10.15.x LTS preferred)
  - **Note**: It *will not work* with Node < 10.x. Using 11.x builds may cause issues as they may introduce instability or breaking changes.
> If you want an easy way to install and update Node, [NVS - Node Version Switcher](../nodejs/installing-via-nvs.md) or [NVM - Node Version Manager](../nodejs/installing-via-nvm.md) is recommended.
- [AutoRest](https://aka.ms/autorest) v3 beta <br>`npm install -g autorest@beta`<br>&nbsp;
- PowerShell 6.0 or greater
  - If you don't have it installed, you can use the cross-platform npm package <br>`npm install -g pwsh`<br>&nbsp;
- .NET Core SDK 2.0 or greater
  - If you don't have it installed, you can use the cross-platform npm package <br>`npm install -g dotnet-sdk-2.2`<br>&nbsp;

## Run Generation
In this directory, run AutoRest:
> `autorest`

---
### AutoRest Configuration
> see https://aka.ms/autorest

``` yaml
commit: 51cdc876974de35d1815df071fb77537d159505c
require:
  - $(this-folder)/../../readme.azure.noprofile.md
  - https://github.com/Azure/azure-rest-api-specs/blob/51cdc876974de35d1815df071fb77537d159505c/specification/postgresql/resource-manager/readme.md
input-file:
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Administrators.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Backups.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Capabilities.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/CheckNameAvailability.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Configuration.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Databases.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/FirewallRules.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/FlexibleServers.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/LongTermRetentionOperation.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Migrations.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Operations.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/PrivateDnsZone.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/PrivateEndpointConnections.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/PrivateLinkResources.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/Replicas.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/ServerLogs.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/ServerStartStopRestart.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/ThreatProtection.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/VirtualEndpoints.json
  - $(repo)/specification/postgresql/resource-manager/Microsoft.DBforPostgreSQL/stable/2024-08-01/VirtualNetwork.json
module-version: 0.1.0
title: PostgreSQL 
subject-prefix: 'PostgreSQL'

# For new modules, please avoid setting 3.x using the use-extension method and instead, use 4.x as the default option
use-extension:
  "@autorest/powershell": "3.x"

directive:
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^CheckNameAvailability_Execute$/g, "NameAvailability_Test")
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^CheckNameAvailabilityWithLocation_Execute$/g, "NameAvailabilityLocation_Test")
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^CheckMigrationNameAvailability$/g, "MigrationNameAvailability_Test")
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^FlexibleServer_TriggerLtrPreBackup$/g, "flexibleServerLtrPreTriggerBackup_Test")
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^FlexibleServer_StartLtrBackup$/g, "flexibleServerLtrTriggerBackup_Start")
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^LocationBasedCapabilities_Execute$/g, "LocationBasedCapabilities_Get")
  - from: Microsoft.DBforPostgreSQL/stable/2024-08-01/FlexibleServers.json
    where: $.paths..operationId
    transform: return $.replace(/^(Servers)_/g, "flexible$1_")
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^(Backups|Configurations|Databases|FirewallRules|ltrBackupOperations|Migrations|Operations)_/g, "flexibleServer$1_")
  - from: swagger-document
    where: $.paths..operationId
    transform: return $.replace(/^(PrivateEndpointConnections|PrivateLinkResources|Replicas|LogFiles|ServerThreatProtectionSettings|VirtualEndpoints)_/g, "flexibleServer$1_")
  - from: Microsoft.DBforPostgreSQL/stable/stable/2024-08-01/VirtualNetwork.json
    where: $.paths..operationId
    transform: return $.replace(/^VirtualNetworkSubnetUsage_Execute$/g,"flexibleServerVirtualNetworkSubnetUsage_Get")
  - from: Microsoft.DBforPostgreSQL/stable/stable/2024-08-01/PrivateDnsZone.json
    where: $.paths..operationId
    transform: return $.replace(/^GetPrivateDnsZoneSuffix_Execute$/g,"flexibleServerPrivateDnsZoneSuffix_Get")
  - from: Microsoft.DBforPostgreSQL/stable/2021-06-01/postgresql.json
    where: 
      verb: Restore$
      subject: ^FlexibleServer$
    hide: true
  - where:
      verb: Get$
      subject: ^FlexibleServerVirtualNetworkSubnetUsage$|^FlexibleServerLocationBasedCapability$
    hide: true
  - where:
      verb: Execute$
      subject: ^PrivateDnsZoneSuffix$
    hide: true
  - where:
      verb: Test$
      subject: ^FlexibleServerNameAvailability$
    hide: true
  - where:
      verb: Set
      subject: Configuration$|FirewallRule$|VirtualNetworkRule$|^flexibleServerFirewallRule$
    set:
      verb: Update
  - where:
      subject: ^Database$|^ServerSecurityAlertPolicy$|^ServerAdministrator$|^LocationBasedPerformanceTier$|^LogFile$|^NameAvailability$|^FlexibleServerKey$|^FlexibleServerVirtualNetworkSubnetUsage$|^ServerBasedPerformanceTier$
    hide: true
  - where:
      verb: New$|Update$
      subject: ^Server$|^Configuration$|^FirewallRule$|^FlexibleServer$|^FlexibleServerFirewallRule$
    hide: true
  - where:
      verb: New$
      variant: ^Create$|^CreateViaIdentity
      subject: ^Server$|^Configuration$|^FirewallRule$|^Database$|^LocationBasedPerformanceTier$|^LogFile$|^SecurityAlertPolicy$|^Administrator$|^NameAvailability$|^VirtualNetworkRule$
    hide: true
  - where:
      verb: Update$
      subject: ^FlexibleServerConfiguration$
    hide: true
  - where:
      verb: New$|Update$
      variant: ^(?!.*?Expanded)
    hide: true
  - where:
      subject: ^ConfigurationsList$|^RecoverableServer$
    remove: true
  - where:
      parameter-name: VirtualNetworkSubnetId
      subject: VirtualNetworkRule
    set:
      parameter-name: SubnetId
  - where:
      model-name: Server
    set:
      format-table:
        properties:
        - Name
        - Location
        - AdministratorLogin
        - Version
        - StorageProfileStorageMb
        - SkuName
        - SkuTier
        - SslEnforcement
  - where:
      model-name: ServerAutoGenerated
    set:
      format-table:
        properties:
          - Name
          - Location
          - SkuName
          - SkuTier
          - AdministratorLogin
          - Version
          - StorageProfileStorageMb
  - where:
      model-name: Configuration
    set:
      format-table:
        properties:
        - Name
        - Value
        - AllowedValue
        - Source
        - DefaultValue
  - where:
      model-name: ConfigurationAutoGenerated
    set:
      format-table:
        properties:
        - Name
        - Value
        - AllowedValue
        - Source
        - DefaultValue
  - where:
      model-name: FirewallRule
    set:
      format-table:
        properties:
        - Name
        - StartIPAddress
        - EndIPAddress
  - where:
      model-name: DatabaseAutoGenerated
    set:
      format-table:
        properties:
          - Name
          - Charset
          - Collation
          - Id
  - where:
      subject: ^FlexibleServer$
      parameter-name: ServerName
    set:
      parameter-name: Name
      alias: ServerName
  - where:
      subject: ^FlexibleServerFirewallRule$
      parameter-name: FirewallRuleName
    set:
      parameter-name: Name
      alias: FirewallRuleName
  - where:
      subject: ^FlexibleServerDatabases$
      parameter-name: DatabaseName
    set:
      parameter-name: Name
      alias: DatabaseName
  - where:
      subject: ^FlexibleServerBackups$
      parameter-name: BackupName
    set:
      parameter-name: Name
      alias: BackupName
  - where:
      subject: ^FlexibleServerltrBackupOperations$
      parameter-name: BackupName
    set:
      parameter-name: Name
      alias: BackupName
  - where:
      subject: ^FlexibleServerMigrations$
      parameter-name: MigrationName
    set:
      parameter-name: Name
      alias: MigrationName
  - where:
      subject: ^FlexibleServerConfiguration$
      parameter-name: ConfigurationName
    set:
      parameter-name: Name
      alias: ConfigurationName
  - where:
      subject: ^FlexibleServerVirtualEndpoints$
      parameter-name: VirtualEndpointName
    set:
      parameter-name: Name
      alias: VirtualEndpointName
  - where:
      subject: ^FlexibleServerServerThreatProtectionSettings$
      parameter-name: ThreatProtectionName
    set:
      parameter-name: Name
      alias: ThreatProtectionName
  - from: source-file-csharp
    where: $
    transform: $ = $.replace(/OperationOrigin System/, 'OperationOrigin System1');
```
