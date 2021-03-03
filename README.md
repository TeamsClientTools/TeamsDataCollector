# Introduction
The Microsoft Teams Data Collector is a PowerShell script useful for easily collecting and packaging various data for troubleshooting Microsoft Teams issues.

This tool does not transmit or share the data collected, it simply produces a ZIP file containing the data.

[![Version](https://img.shields.io/github/v/release/TeamsClientTools/TeamsDataCollector?label=latest%20version)](https://github.com/TeamsClientTools/TeamsDataCollector/releases/latest/download/TeamsDataCollector.zip)
[![Downloads](https://img.shields.io/github/downloads/TeamsClientTools/TeamsDataCollector/total)](https://github.com/TeamsClientTools/TeamsDataCollector/releases/latest/download/TeamsDataCollector.zip)

# Getting Started
PowerShell **5.0** (or greater) must be installed on the host machine. Click [here](https://github.com/powershell/powershell) for details
on how to get the latest version for your computer. 

# Usage
1. [Download](https://github.com/TeamsClientTools/TeamsDataCollector/releases/latest/download/TeamsDataCollector.zip) the script package.
2. Extract it on to the computer experiencing Teams issues.
3. Run the CollectTeamsClientData.ps1 script.
4. Once the script is complete, it should produce a ZIP file in the same folder as the script.

# Advanced Usage
```
CollectTeamsClientData.ps1 [-Help]

CollectTeamsClientData.ps1 [[-Destination] <path>] [[-Scenario] <scenario name>]

  -Help       : Displays this help message. This will list available scenarios.

  -Destination: Provides the destination for the ZIP file produced by this script.
                If one is not provided, it will default to the script location.

  -Scenario   : Provides the scenario name to collect.
                If one is not provided, it will default to "All".
```                
# Data Collected
The script collects various files, registry keys, and enumerates various directories.
It will list each file and registry key that it collects, and each directory it enumerates.

It also collects:
- General computer information (Get-ComputerInfo)
- Display information (Get-WmiObject win32_videocontroller)
- Drive information (Get-PSDrive, Get-PhysicalDisk, Get-Volume)
- Network information (Get-NetAdapter, Get-NetIPAddress)
- Running processes (Get-Process)
- Application and System event logs

The data collected by the script may contain End-User Identifiable Information (EUII).
This could include, but is not limited to:
- Computer name
- User name
- Email addresses
- SIP addresses
- IP addresses
- MAC addresses
- Telephone numbers (calling or called)
- User IDs (such as AAD Object GUID)

The script does NOT collect passwords or any other credential information.

The ZIP file produced by the script can be opened and its contents reviewed.
