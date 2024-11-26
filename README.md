# Active-Directory-Lab-in-Azure

## Quick Active Directory Lab Environment in Azure

This project demonstrates how to quickly set up an Active Directory lab environment in Microsoft Azure using an Azure Quickstart Template. It includes configuring a VM, creating a new Active Directory Forest, and automating AD setup with PowerShell scripts.

---

### Description

**Active Directory (AD)** is a Microsoft service used to manage and organize network resources, users, and security across an enterprise. It provides centralized authentication and access control, making it a core component in many IT environments.

In this lab setup, I utilized Microsoft's Azure Quickstart template to quickly deploy a new Active Directory Forest on a VM in Azure. The steps include setting up the VM, configuring DNS, and applying additional configurations using PowerShell scripts for enhanced AD management.

---

### Setup Steps

1. **Deploy Active Directory Quickstart Template**
   - Navigate to the [Active Directory Azure Quickstart Template](https://learn.microsoft.com/en-us/samples/azure/azure-quickstart-templates/active-directory-new-domain/).
   - Click **"Deploy to Azure"**, sign in to your Azure account, and fill in the required configurations:
     - **Admin Username and Password**
     - **Domain Name** and **DNS Prefix**
     - **VM Size** and other settings (network interface, IP address, etc.)
   - After reviewing, click **"Create"** to deploy the environment.
   
2. **RDP into the VM**
   - Once deployment is complete, use the **RDP** client to log in to the VM with the admin credentials you configured during deployment.
   
3. **Verify Active Directory Setup**
   - Inside the VM, open **Active Directory Users and Computers** to verify the presence of the domain controller and configured domain.

---

### Configuration with PowerShell Script

Instead of manually configuring the AD environment, I used a PowerShell script to automate the following tasks:
- **Create Organizational Units (OUs)**: 'Workstations,' 'Servers,' 'People,' 'Groups,' and 'Resources'
- **Create Users**: Users are automatically added to the appropriate OUs and groups based on their roles (e.g., admin users are added to the admin group).
- **Apply GPOs**: Group Policy Objects (GPOs) are automatically applied from a [GitHub repository](https://github.com/) to enforce organizational policies.

---

### Key Technologies

- **Microsoft Azure**: Hosting the lab environment and configuring the VM.
- **PowerShell**: Automating the Active Directory configuration.
- **Windows Server 2019**: The operating system used in the VM.
- **Group Policy Objects (GPOs)**: Applied from an external GitHub repository for centralized configuration.

---

### Screenshots

#### 1. Deploying Active Directory via Azure Template

<p align="center">
<img height="85%" width="85%" alt="Azure Template" src="https://github.com/user-attachments/assets/7ff05d1f-02ea-4292-97a7-7da97bd07431">
</p>

#### 2. VM Startup and Active Directory Verification

<p align="center">
<img height="85%" width="85%" alt="Server Startup" src="https://github.com/user-attachments/assets/409c62be-402f-4c75-9f24-e7cc37b201f2">
</p>

#### 3. Checking AD and DNS

<p align="center">
<img height="85%" width="85%" alt="AD and DNS" src="https://github.com/user-attachments/assets/40f1f653-56fa-4889-b81a-81c5b6316194">
</p>

---

### PowerShell Configuration

#### 1. Running PowerShell Script

<p align="center">
<img height="85%" width="85%" alt="PowerShell Script" src="https://github.com/user-attachments/assets/fd207181-f7f9-4e0f-9952-2d732bf13b2d">
</p>

- After running the script and providing the **Domain Name** used in the Azure setup, the script creates users in the specified Organizational Units (OUs). Below is an example of the users created in the 'People' OU.

#### 2. Created Users in the 'People' Organizational Unit

<p align="center">
<img height="85%" width="85%" alt="Users Created" src="https://github.com/user-attachments/assets/3ffd864d-4e19-4049-8a06-f5c07430e0f0">
</p>

---

### Admin Group Configuration

#### 1. Adding Users to Admin Groups

<p align="center">
<img height="85%" width="85%" alt="Admins Group" src="https://github.com/user-attachments/assets/c77e482a-ab55-4e42-baf9-263d03fb6d3f">
</p>

- Users with **"-ADM"** in their usernames (e.g., **John-ADM**) are added to the **SEC-ServerAdmins** group. This group is linked to a GPO that grants server admin rights.

---

### Prerequisites

Before running the script, ensure the following:
- **Azure Subscription**: You will need an active Azure subscription to deploy the VM.
- **PowerShell**: Ensure PowerShell is enabled and configured on the VM for running scripts.

---


