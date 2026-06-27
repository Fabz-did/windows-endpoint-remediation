# windows-endpoint-remediation
Automated script to resolve Windows Update database deadlocks and system file corruption 
# windows-endpoint-remediation
Automated script to resolve Windows Update database deadlocks and system file corruption.

## ⚠️ Disclaimer
Running scripts that modify system files and Windows Update components can impact system stability. Use this script at your own risk. It is recommended to test it in a virtual machine or a staging environment first.

## 🚀 Features
* **Stops Windows Update Services:** Safely halts `wuauserv`, `bits`, and `cryptsvc`.
* **Clears Update Cache:** Purges the `SoftwareDistribution` and `catroot2` directories to clear deadlocks.
* **System File Repairs:** Executes `SFC /scannow` and `DISM` health checks to repair underlying corruption.
* **Resets Network/Catalog:** Resets Winsock and routing tables if necessary.
* **Restarts Services:** Cleanly restarts background services to initiate a fresh update check.

## 📋 Prerequisites
* **OS:** Windows 10 / 11 or Windows Server.
* **Permissions:** Must be run from an **Elevated PowerShell** or Command Prompt instance (Run as Administrator).

## 🛠️ Usage
1. Clone or download the repository script.
2. Open PowerShell as an Administrator.
3. Execute the script:
   ```powershell
   .\remediate-endpoint.ps1
