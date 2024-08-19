# Domain Controller Setup with Active Directory, NAT, DHCP, and Automated User Creation via PowerShell

## Overview

This project demonstrates the setup of a **Domain Controller** running **Active Directory (AD)**, **NAT**, **DHCP**, and a **PowerShell script** to automate the creation of 1000 users. The environment is built using **Oracle VirtualBox**, providing a virtualized platform for testing and configuration.

## Features

1. **Domain Controller with Active Directory**: A central server is configured to manage user accounts, groups, and security policies.
2. **Network Address Translation (NAT)**: NAT is used to allow virtual machines to communicate with external networks.
3. **Dynamic Host Configuration Protocol (DHCP)**: DHCP is configured to automatically assign IP addresses within the network.
4. **Automated User Creation**: A PowerShell script is used to generate 1000 user accounts in Active Directory for testing or demonstration purposes.
5. **Virtualization via Oracle VirtualBox**: The entire setup is virtualized, making it portable and easy to replicate on different machines.

## Components

- **Windows Server (Virtualized)**: Configured as the domain controller with Active Directory and DHCP services installed.
- **DHCP Service**: Manages dynamic IP address allocation for network clients.
- **PowerShell Script**: Automates the process of creating 1000 users with randomized data.
- **Oracle VirtualBox**: Used to create and manage the virtualized environment.

## Prerequisites

Before proceeding with the setup, ensure that the following are installed and configured:

- **Oracle VirtualBox**: Download and install from [Oracle VirtualBox](https://www.virtualbox.org/).
- **Windows Server ISO**: A licensed copy of Windows Server to use as the base operating system.
- **PowerShell**: Installed on the Windows Server to run the automated script.
- **Active Directory Domain Services**: Enabled on the Windows Server.
- **DHCP Role**: Added and configured on the Domain Controller.

## Setup Instructions

### Step 1: Install Windows Server on VirtualBox
1. Download and install Oracle VirtualBox.
2. Create a new virtual machine and install Windows Server using your ISO.
3. Configure network settings to use NAT for internet connectivity.

### Step 2: Configure the Domain Controller
1. Install **Active Directory Domain Services (AD DS)**.
2. Promote the server to a domain controller and configure a new domain.
3. Set up DNS as part of the AD DS installation.

### Step 3: Enable NAT
1. Ensure the virtual network is set to **NAT** in the VirtualBox settings for internet access.
2. Configure IP addressing and routing for the internal network.

### Step 4: Set Up DHCP
1. Add the **DHCP Role** to your Windows Server.
2. Configure DHCP to manage IP address allocation on your internal network.
3. Set up IP scopes, exclusions, and lease times according to your network needs.

### Step 5: Run the PowerShell Script to Create Users
1. Clone or download the PowerShell script provided in this repository.
2. Open PowerShell with administrative privileges.
3. Well be using Josh Madakor's powershell script.

### Step 6: Verify Setup
1. Open **Active Directory Users and Computers** to verify the user accounts.
2. Open the **DHCP Management Console** to confirm that IP addresses are being assigned to network clients.
3. Test network connectivity between clients to ensure **NAT** and **DHCP** are functioning correctly.

### Troubleshooting

- If users are not being created, ensure the PowerShell execution policy is set to allow script execution using:

   ```powershell
   Set-ExecutionPolicy Unrestricted
