Creating the Windows Server 2022 Virtual Machine in VMware Workstation

This document explains how to create the Windows Server 2022 virtual machine inside VMware Workstation.  
This VM will later become the Domain Controller (LAB-DC) for the Active Directory homelab.

---

# 1. Prerequisites
Before creating this VM, ensure you have:

- VMware Workstation installed  
- VMnet1 (Host-only network) configured  
- Windows Server 2022 ISO downloaded  

Place the ISO in your lab folder, for example:
ISOs/Windows_Server_2022_Eval.iso
Or use the path wehre it is saved.

---

# 2. Start Creating a New Virtual Machine

Open VMware Workstation and click:
Create a New Virtual Machine

Choose:
Typical (recommended)

Click **Next**.
---

# 3. Select the Installation ISO
Select:
Installer disc image file (ISO)

Browse to your ISO:
ISOs/Windows_Server_2022_Eval.iso

Click **Next**.

---

# 4. Select Guest Operating System

Set the following:

- **Guest OS**: Microsoft Windows  
- **Version**: Windows Server 2022  

If Windows Server 2022 does not appear, choose:

Windows Server 2019 (64-bit)

Click **Next**.

---

# 5. Name the Virtual Machine

Enter:

LAB-DC

Choose a tidy location inside your repo folder, for example:

active-directory-attack-chain/VMs/LAB-DC

Click **Next**.

---

# 6. Configure the Virtual Disk

Set:

Maximum disk size: 20 GB


Choose:

Store virtual disk as a single file

Click **Next**.

---

# 7. Customize Hardware (IMPORTANT)

Click:

Customize Hardware...

Modify the following:

### Memory

4096 MB minimum
8192 MB recommended


### Processors

2 processors / 2 cores

### Network Adapter
Change to:

Custom → VMnet1 (Host-only)

This isolates the Active Directory lab network.

Click **Close**, then **Finish**.

---

# 8. Power On the VM

Click:

Power on this virtual machine

The Windows Server 2022 installer will boot from the ISO.

---

# 9. Begin Windows Server Installation

Inside the setup:

1. Choose language → **Next**
2. Click:

Install Now

3. Select:

Windows Server 2022 Standard Evaluation (Desktop Experience)

4. Accept License → Next  
5. Choose:

Custom: Install Windows Only

6. Select the 60GB virtual drive → **Next**

Windows will install and reboot automatically.

---

# 10. Set Administrator Password

After installation completes, set the password for the **Administrator** account.

Example (lab only):

Password123!

Press **Finish**.

---

# 11. Log Into Windows Server

In VMware, press:

Ctrl + Alt + Insert

(This replaces Ctrl+Alt+Delete)

Log in as:

Administrator

---

# 12. Install VMware Tools

This step is required for proper performance.

In VMware Workstation:

VM → Install VMware Tools

Inside Windows Server:
1. Open the VMware Tools virtual DVD  
2. Run **setup64.exe**  
3. Choose:

Typical Installation

4. Reboot the VM

---

# 13. Rename the Server

Open:

Server Manager → Local Server → Computer Name

Click **Change** and set:

LAB-DC

Restart the server.

---

# 14. Assign a Static IP Address

Go to:

Control Panel → Network and Internet → Network Connections

Right-click **Ethernet** → Properties → IPv4.

Enter:

IP Address: 10.0.0.10
Subnet Mask: 255.255.255.0
Default Gateway: (leave blank)
Preferred DNS: 10.0.0.10

Click OK.

---

# 15. Windows Server 2022 VM Creation Complete

The VM is now:

- Installed successfully  
- VM tools enabled  
- Renamed to **LAB-DC**  
- Attached to **VMnet1**  
- Assigned static IP: **10.0.0.10**  
- Ready for Active Directory Domain Services installation  

Proceed next to:

04-promote-to-domain-controller.md

where LAB-DC will be promoted to the domain **lab.local**.
