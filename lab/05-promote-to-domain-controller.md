Promotion of LAB-DC to a Domain Controller (Continuation from Add Roles and Features)

This document begins **immediately after** the completion of:

04-add-roles-and-features.md

At this point:

- The **Active Directory Domain Services (AD DS)** role is installed  
- Server Manager shows the post-install notification  
- The server is ready to be promoted to a Domain Controller  

---

# 1. Begin Domain Controller Promotion

At the top-right of **Server Manager**, click the yellow notification flag.

Select:

Promote this server to a domain controller

This opens the **Active Directory Domain Services Configuration Wizard**.

---

# 2. Deployment Configuration

Choose:

Add a new forest

Enter the root domain name:

lab.local

Click **Next**.

---

# 3. Domain Controller Options

Configure as follows:

### Functional Levels

Forest functional level: Windows Server 2016 or Windows Server 2022
Domain functional level: Windows Server 2016 or Windows Server 2022
NOTE: USe Windows Server 2016 if 2022 is not available

### Additional Options  
Check:
- Domain Name System (DNS) Server  
- Global Catalog (GC)

Do NOT check:
- Read-only domain controller (RODC)

### DSRM Password
Set the Directory Services Restore Mode password:

Example (lab use only):

Password123!

Click **Next**.

---

# 4. DNS Options

You will see this warning:

A delegation for this DNS server cannot be created...


This is normal for a new forest.

Click **Next**.

---

# 5. Additional Options

The wizard will auto-generate the NetBIOS name:

LAB

Leave it unchanged.

Click **Next**.

---

# 6. Paths

Use the default AD DS database, log, and SYSVOL paths:

Database: C:\Windows\NTDS
Logs: C:\Windows\NTDS
SYSVOL: C:\Windows\SYSVOL

Click **Next**.

---

# 7. Review and Install

Review the configuration summary.

Click:

Next → Install

The server will:

- Install required components  
- Promote itself to a domain controller  
- Automatically reboot when finished  

**Do not interrupt the process.**

---

# 8. First Logon After Promotion

After reboot, use:

LAB\Administrator

Enter your password.

You are now logged into a fully promoted Domain Controller.

---

# 9. Post-Promotion Verification

Open **PowerShell** and run:

### Verify Domain:

Get-ADDomain

### Verify Forest:

Get-ADForest

### Check DNS:

nslookup lab.local

It should resolve to:


10.0.0.10

### Confirm AD Tools
Open:

Server Manager → Tools → Active Directory Users and Computers

If it opens correctly, the promotion succeeded.

---

# 10. Domain Controller Promotion Complete

LAB-DC is now:

- The first Domain Controller
- DNS server for the domain
- Global Catalog server
- Hosting the forest: lab.local
