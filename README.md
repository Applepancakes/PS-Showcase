#Powershell-Showcase

This showcase is to demonstrate two scripts that would assist and streamline the hardware reimaging process

First, the script used to pull the hardware ID .CSV data to manage the device via Microsoft Auto Pilot Process

Second, a System information collection script for management of hardware resources (needing to upgrade RAM or SSD for example) and for documentation purposes.


Both very helpful in the Provisioning process for an IT specialist


------- Hardware Identification pull for Microsoft AutoPilot

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

New-Item -Type Directory -Path "C:\HWID"


Set-Location -Path "C:\HWID"


$env:Path += ";C:\Program Files\WindowsPowerShell\Scripts"


Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned

Install-PackageProvider -Name NuGet -MinimumVersion 2.8.5.201 -Force

Install-Script -Name Get-WindowsAutopilotInfo -Force

Get-WindowsAutopilotInfo -OutputFile AutopilotHWID.csv

Copy-Item -Path "C:\HWID\AutopilotHWID.csv" -Destination "D:\Temp" -Force


---------------------------------------------------------------------------------------------

# System Information Collector


![image](https://github.com/Applepancakes/PS-Showcase/assets/158091426/1541488d-5e89-44ab-b060-a48cf83663d3)

