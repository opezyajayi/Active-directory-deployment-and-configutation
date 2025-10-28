# Active Directory Simulation – Morelzy Global

This project is the deployment of a Windows Server Domain Controller (Active Directory) for a company called MORELZY GLOBAL. It includes domain setup, client configuration, OU design, group policies, and access control in an enterprise environment.

---

## Company Structure

MORELZY GLOBAL is a small IT services firm with the following structure:

- 1 x Windows Server (AD Domain Controller)
- 1 x Windows 8 Client PC (HR Department)
- 1 x Windows 8 Client PC (IT Department)

---

## Project Objectives

- Configure an AD Domain Controller on Windows Server
- Join client PCs to the domain
- Create Organizational Units (OUs)
- Implement basic Group Policies for access control
- Simulate a centralized IT environment

---

## Network Design

```
Internet
   ↓
Router (Gateway: 10.0.2.7)
   ↓
Switch
 ┌──────┬─────────────┬──────────────┐
 │      │             │              │
Server  PC1 (Win 8)   PC2 (Win 8)
```

| Device        | IP Address      | Role                        |
|---------------|---------------- |-----------------------------|
| Windows Server| 10.0.2.7        | AD Domain Controller (DC)   |
| Windows 8 PC  | 10.0.2.8        | Client (HR)                 |
| Windows 8 PC  | 10.0.2.9        | Client (IT)                 |

---

## Domain Configuration

- **Domain Name**: `MORELZY.GLOBAL`
- **Server Name**: `MORELZY`
- **Static IP**: `10.0.2.7`
- **AD Roles Installed**: AD DS, DNS (DHCP)

---

## Organizational Units (OUs)

Created using **Active Directory Users and Computers**:

```
Morelzy.global
├── OU: GHANA
│   └── Users: JOHN.IT
    

├── OU: NIGERIA
│   └── Users:JANE.HR
```

---

## Group Policy (GPO)

Created and linked using **Group Policy Management Console (gpmc.msc)**:

- **GPO Name**: `DisableShutdownAndRestart`
- **Linked to**: OU: GHANA
- **Policy Configured**:
  - `Computer Configuration` > `Administrative Templates` > `Start Menu and task bar` > `Remove and prevent access to shut down, restart, sleep and hibernate comands`
  - Set **" Remove and prevent access to shut down, restart, sleep and hibernate comands "** to **Enabled**

Result: Access to shutdown, restart or sleep is disabled for all users in the **GHANA Accounts OU**.

---

## Screenshots

- AD Domain Structure
- GPO Editor Screenshot
- PC joined to domain
- Result of denied shutdown/restart access

---

## Key Takeaways

 - Gained practical experience with Windows Server roles and domain setup
- Implemented centralized access control using Group Policy
- Learned how to structure users and departments with OUs
- Applied IAM concepts in a real-world simulated environment

---

## Author

Opeyemi Ajayi
Cybersecurity Analyst
