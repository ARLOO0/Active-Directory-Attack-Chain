# 01 — Installing VMware Workstation (Broadcom Download Guide)

VMware is now owned by Broadcom, and all downloads are distributed through the Broadcom Support Portal.  
This guide documents the exact process for downloading VMware Workstation Pro / Player.

---

# 1. Create a Broadcom Account

VMware downloads now require a Broadcom login.

## Steps:
1. Go to:  
   https://accounts.broadcom.com

2. Click **Create an Account**.

3. Fill in:
   - Email  
   - First/Last Name  
   - Password  
   - Country

4. Verify your email.

This account gives access to all VMware downloads.

---

# 2. Access the Broadcom Support Portal

1. Go to:  
   https://support.broadcom.com

2. Click **Login**.

3. Enter the Broadcom credentials you created.

4. After logging in, you will see the main Broadcom support dashboard.

---

# 3. Navigate to the VMware Download Section

1. On the dashboard, click:
   **"VMware Cloud Foundation"**  
   *(This is the category where VMware Workstation downloads now live.)*

2. On the left sidebar, scroll down to **"My Downloads"**.

3. You will now see a list of VMware products.

---

# 4. Find VMware Workstation Pro / Player

Inside the **VMware Downloads** section:

Look for:

- **VMware Workstation Pro**
- **VMware Workstation Player**

Current versions appear as:
- *"VMware Workstation Pro 17.x"*  
- *"VMware Workstation Player 17.x"*

Click on the product you want.

---

# 5. Download the Installer

Inside the product download page:

### For Windows:
Click:
VMware-workstation-full-17.x.x-xxxxxxx.exe

### Windows Installation
1. Run:
VMware-workstation-full-17.x.x-xxxxxxx.exe
2. Accept the license agreement.
3. Choose **Typical Installation**.
4. Leave default settings:
- Enhanced Keyboard Driver (optional)
- Check for product updates
5. Allow installation of VMware network adapters (VMnet0/1/8).
6. Click **Install**.
7. Click **Finish**.

VMware is now installed.

---

# 6. Verify VMware Network Adapters

Open the VMware Virtual Network Editor:

VMware Workstation → Edit → Virtual Network Editor

Ensure these networks exist:
- **VMnet0** — Bridged
- **VMnet1** — Host-only (used for AD homelab)
- **VMnet8** — NAT

We will use **VMnet1** for the AD lab.

---

# 7. Launch VMware Workstation

Open VMware Workstation from the Start Menu.

You are now ready to:
- Create VMs
- Configure VMnet1
- Begin the Active Directory homelab build

---

# 8. Install VMware Tools (Inside VMs)

After creating any VM (Windows or Linux), install VMware Tools.

### Steps:
1. Power on the VM.
2. In VMware menu:
VM → Install VMware Tools

markdown
Copy code
3. Inside the VM:
- Run the installer  
- Accept defaults  
- Reboot the VM when finished  

### Why VMware Tools is required:
- Enables shared clipboard
- Enables drag-and-drop
- Improves display resolution
- Improves network performance
- Enables smooth mouse integration

---

# 9. Installation Complete

At this point, you have:

- A Broadcom account  
- Installed VMware Workstation  
- Verified network adapters  
- Learned how to install VMware Tools  


