# DeploySQLMaintenanceSolution

Powershell based deployment of SQL Server Maintenance Solution

## Example Command

.\MaintenanceSolution-Execute.ps1 -Computer computer1 -Instance INST1 -InstallSourcePath '\\computerShare\SQLInstall'

## Parameters

|Parameter|Type|Default/Status|Description|
|---|---|---|---|
|Computer|\[string\[\]\]|Required - defaults to localhost|The computer(s) that will have SQL Installed|
|Instance|\<string\>|Optional|If provided will install SQL in an instance, otherwise default instance is used.|
|InstallSourcePath|\<string\>|Optional - defaults to \\currentmachine\DeploySQL|Path where installation media and scripts are located.|
|InstallCredential|[psCredential]|Required|Credential used to install SQL Server and perform all configurations. Account should be a member of the group specified in -DBATeamGroup as well as a local administrator of the target server.|

## Getting Started

1. Ensure installation files are all unblocked (if downloaded from GitHub)

    Get-ChildItem [path to your folder] -recurse | Unblock-File

2. Ensure powershell execution mode is set to unrestricted

     Set-ExecutionPolicy Unrestricted

3. Create a file share at the root of the installation path... so c:\git\deploySQLMS should be available at \\\computer\deploySQLMS

4. Copy the contents of [InstallPath]\PSModules to C:\ProgramFiles\WindowsPowerShell\Modules

5. Copy installation media to the [InstallPath]\InstallMedia folders as appropriate.

## Assumptions

- Credential used for installation has administrative rights to target machines.
