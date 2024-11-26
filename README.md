# Active-Directory-Lab-in-Azure
Using Microsoft's template to quickstart an Azure VM with an Active Directory Forest for a lab environment



# Quick Active Directory Lab Environment in Azure

## Description
**Active Directory is a Microsoft service that manages and organizes network resources, users, and security across an enterprise, using a centralized database for authentication and access control.**

To set up this environment, I navigated to Microsoft's Active Directory Quickstart template at [this link](https://learn.microsoft.com/en-us/samples/azure/azure-quickstart-templates/active-directory-new-domain/), then clicked "Deploy to Azure" to sign in and configure an Azure VM with a new AD Forest. During the setup, I created an admin username and password, specified a domain name and DNS prefix, selected a VM size, and left the rest of the settings at their defaults, including network and IP configurations. After hitting "Review + Create," I deployed the environment and RDP’d into the VM using the admin credentials. Inside the VM, I accessed Active Directory Users and Computers to confirm the domain controller was set up. Instead of manually configuring the AD, I ran a PowerShell script to create Organizational Units (OUs) like 'Workstations,' 'Servers,' 'People,' 'Groups,' and 'Resources,' add users to these OUs, assign them to groups based on roles (e.g., admin), and apply Group Policy Objects (GPOs) from a GitHub repository.

---

### Start with simple template from Microsoft 

<p align="center">
<img height="85%" width="85%" alt="Screenshot 2024-11-19 at 10:50:25 AM" src="https://github.com/user-attachments/assets/7ff05d1f-02ea-4292-97a7-7da97bd07431">
</p>

## Key Technologies
- **Microsoft Azure:** Configures and hosts the Active Directory lab environment.
- **Powershell:** Added alternate/extra configuration for the Active Directory environment.

## Operating System Used
- **Windows Server 2019**

---

### Lab VM Startup

<p align="center">
<img height="85%" width="85%" alt="Server Startup" src="https://github.com/user-attachments/assets/409c62be-402f-4c75-9f24-e7cc37b201f2">
</p>

- **Checking Active Directory and DNS:** Open Active Directory and Users and Computers as well as DNS to make sure Azure template set up everything.

<p align="center">
<img height="85%" width="85%" alt="AD and DNS" src="https://github.com/user-attachments/assets/40f1f653-56fa-4889-b81a-81c5b6316194">
</p>

---

### Powershell Configuration

<p align="center">
<img height="85%" width="85%" alt="Screenshot 2024-11-24 at 3 14 24 PM" src="https://github.com/user-attachments/assets/fd207181-f7f9-4e0f-9952-2d732bf13b2d">
</p>

- **Provide Domain Name:** Ran the script and provided the domain name I used in the Azure setup and after we can see the users that were created in the OU, 'People.'

<p align="center">
<img height="85%" width="85%" alt="Screenshot 2024-11-24 at 4 24 27 PM" src="https://github.com/user-attachments/assets/3ffd864d-4e19-4049-8a06-f5c07430e0f0">
</p>


---

### Groups for the Admins

<p align="center">
<img height="85%" width="85%" alt="Screenshot 2024-11-24 at 10 15 23 PM" src="https://github.com/user-attachments/assets/c77e482a-ab55-4e42-baf9-263d03fb6d3f">
</p>

- **Administrators Group:** We can now see the users with "-ADM" in their name in the Powershell script were added to SEC-ServerAdmins which linked with the GPO to configure server admin rights.


---



