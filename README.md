---
page_type: sample
languages:
- powershell
products:
- azure
description: "Automate On-demand backup for Azure File Shares using PowerShell for Azure Backup"
urlFragment: Use-PowerShell-for-long-term-retention-of-Azure-Files-Backup
---

# Automate On-demand backup for Azure File Shares using PowerShell for Azure Backup

Automate On-demand backup for Azure File Shares using [PowerShell for Azure Backup](https://docs.microsoft.com/azure/backup/backup-azure-afs-automation)

## Update - Feb 2020

Please upgrade the PS modules to a version 2.6.0 or above

## Features

Create recovery points while backing up Azure Files with up to 10 years of retention

## Step1
Create an Automation resource with “Run As” account

## Step2
Import modules from Gallery in the Automation resource.

Import the following modules from the Modules gallery in the order given below:
1.Az.Accounts ( 1.7.1)
2.Az.RecoveryServices(2.6.0)


## Step3
Create PowerShell Runbooks in the Automation Resource. You can create multiple Runbooks based on which set of File shares you want to protect.

## Step4
Edit the Runbook and write script to choose which file shares to take a backup. You can create scripts that suit your requirements.
- Save the script
- Test the script using “Test Pane”
- Publish the Runbook

A [sample script](AFB-LTR-WithAzModule.ps1.txt) to backup all file shares in a subscription is provided in the repository

## Step5
Schedule the Runbook. While scheduling the Runbook, you can pass on the parameters required for the PowerShell Script. The sample script takes the retention as an input. So, if you need to schedule a weekly snapshot and retain for 8 weeks, create a weekly schedule as mentioned below and specify the retention as 56 days (8 weeks). You can create monthly and yearly schedules (run every 12 months) in a similar manner. You can monitor the success/failure of these backups using the “Jobs” tab of Runbooks
