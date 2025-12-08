# 04 — Adding Roles and Features (Active Directory Domain Services)

This document explains how to install the **Active Directory Domain Services (AD DS)** role on Windows Server 2022 using the *Add Roles and Features Wizard*.  
This is the required step before promoting the server to a Domain Controller.

The VM used here is:
LAB-DC (Windows Server 2022)
IP: 10.0.0.10
---

# 1. Open Server Manager

Server Manager launches automatically at login.  
If not, open it manually:

Start Menu → Server Manager

---

# 2. Start the Add Roles and Features Wizard

In Server Manager:

Manage → Add Roles and Features

This starts the wizard.

Click **Next**.

---

# 3. Select Installation Type

Choose:
Role-based or feature-based installation

Click **Next**.

---

# 4. Select the Destination Server

Your local server (LAB-DC) will be selected automatically.

Confirm:
Server: LAB-DC

Click **Next**.

---

# 5. Select Server Roles

Scroll through the list and check:

Active Directory Domain Services

A pop-up will appear. Click:

Add Features

Then click **Next**.

---

# 6. Select Features

Leave everything as default.

Do **not** add unnecessary features.

Click **Next**.

---

# 7. AD DS Information Page

You will see a description that AD DS:

- Creates domain controllers  
- Manages user and computer accounts  
- Stores directory data  
- Supports authentication and authorization  

Click **Next**.

---

# 8. Confirm Installation

Click:
Install

Do **not** restart yet.

The installation may take 1–3 minutes.

---

# 9. Installation Complete

Once the installation finishes, a new option appears at the top of Server Manager:

Promote this server to a domain controller

Do **not** click it yet unless following the next document:

05-promote-to-domain-controller.md

---

# 10. Add Roles and Features Completed Successfully

Your Windows Server 2022 machine now has the **Active Directory Domain Services** role installed and is ready for Domain Controller promotion.

Summary:

- AD DS role installed  
- Required features added  
- Server prepared for forest creation (`lab.local`)  
