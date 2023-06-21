# Packer template for Windows Server 2019 using vSphere-ISO provider

## Note: this code is compatible with Packer v1.9.x or later.

This repository contains **HashiCorp Packer** templates to deploy **Windows Server 2019** in **VMware vSphere (with vCenter)**, using the **vsphere-iso** builder.

These templates creates the Template (or VM) directly on the vSphere server and install the latest VMware Tools.

# Content: #

* [autounattend.xml](./autounattend.xml) --> Answer file for unattended Windows setup ***Please edit the password for this file***
* [credentials.json](./credentials.json) --> Credential file ***Please edit the file for your enviroment***
* [windows2019.json](./windows2019.json) --> Windows Server 2019 Packer JSON file Base

Scripts:
* [scripts/disable-network-discovery.cmd](./scripts/disable-network-discovery.cmd) --> Script to Disable network discovery
* [scripts/disable-server-manager.ps1](./scripts/disable-server-manager.ps1) --> Script to Disable Server Manager
* [scripts/disable-winrm.ps1](./scripts/disable-winrm.ps1) --> Script to Disable WinRM
* [scripts/enable-rdp.cmd](./scripts/enable-rdp.cmd) --> Script to Enable Remote Desktop
* [scripts/enable-winrm.ps1](./scripts/enable-winrm.ps1) --> Script to Enable WinRM
* [scripts/install-vm-tools.cmd](./scripts/install-vm-tools.cmd) --> Script to Install VMware Tools
* [scripts/set-temp.ps1](./scripts/set-temp.ps1) --> Script to Set Temp Folders
* [scripts/build.ps1](./scripts/build.ps1) --> Script to disable TLS 1.0 & 1.1 and Windows Firewall

Tested with **VMware ESX 6.7** and **VMware ESX 7.0** | User: Administrator | Password: your_password

# Requirements: #

* Packer        --> https://www.packer.io
* Packer plugin --> https://github.com/rgl/packer-plugin-windows-update/releases

# How to use: #

execute **packer build windows2019.json**
