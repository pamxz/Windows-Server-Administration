# How to Set Up Active Directory Domain Services (AD DS) on Windows Server 2022

This guide provides step-by-step instructions for installing and configuring **Active Directory Domain Services (AD DS)** on **Windows Server 2022**. AD DS enables you to create and manage a domain, centralizing user and computer management within a network.

---

## Prerequisites

Before you begin, ensure the following requirements are met:

- A **Windows Server 2022** machine
- **Administrator privileges**
- A **static IP address** configured on the server  
  *(Refer to the previous guide on setting a static IP address)*
- **DNS server** available (can be installed during AD DS setup)

---

## Step 1: Install Active Directory Domain Services

### 1. Open Server Manager
- Click the **Start** button
- Open **Server Manager**

### 2. Add Roles and Features
- In Server Manager, click **Manage** (top-right)
- Select **Add Roles and Features**
- The **Add Roles and Features Wizard** will open

> 📸 *Image*

### 3. Select Installation Type
- Choose **Role-based or feature-based installation**
- Click **Next**

> 📸 *Image*

### 4. Select Destination Server
- Ensure the current server is selected
- Click **Next**

### 5. Select Server Roles
- Check **Active Directory Domain Services**
- When prompted, click **Add Features**

> 📸 *Image*

- Click **Next**

### 6. Add Features
- Leave the default features selected
- Click **Next**

### 7. AD DS Information
- Review the AD DS information
- Click **Next**

### 8. Confirm Installation
- Review your selections
- Click **Install**

> 📸 *Image*

⏳ The installation may take a few minutes.  
⚠️ **Do not close the wizard** — you will need it to promote the server to a domain controller.

---

## Step 2: Promote the Server to a Domain Controller

### 1. Promote to Domain Controller
- Click **Promote this server to a domain controller**

> 📸 *Image*

### 2. Deployment Configuration
- Select **Add a new forest**
- Enter your **Root domain name** (e.g., `example.com`)
- Click **Next**

> 📸 *Image*

### 3. Domain Controller Options
- Set **Forest functional level** and **Domain functional level**  
  *(Default: Windows Server 2022)*
- Ensure **DNS server** is checked
- Enter a **Directory Services Restore Mode (DSRM)** password
- Click **Next**

> 📸 *Image*

### 4. DNS Options
- A DNS delegation warning may appear
- Safely ignore it and click **Next**

> 📸 *Image*

### 5. Additional Options
- Confirm the **NetBIOS domain name**
- Click **Next**

### 6. Paths
- Leave Database, Log files, and SYSVOL paths at default (or customize)
- Click **Next**

### 7. Review Options
- Review your configuration
- Click **Next** to run the prerequisite check

### 8. Install AD DS
- Once all prerequisite checks pass, click **Install**

> 📸 *Image*

🔁 The server will **automatically restart** after installation completes.

---

## Step 3: Verify the AD DS Installation

After the reboot:

### 1. Check Server Manager
- Log back in
- Open **Server Manager**
- Confirm **AD DS** appears in the left-hand menu
- Click **AD DS** to verify service health and status

> 📸 *Image*

---

## Additional Notes

- **Static IP Address**  
  A static IP is required for reliable domain and DNS operation.

- **DNS Configuration**  
  The Domain Controller now also functions as a DNS server for the domain.

---

## Conclusion

You have successfully installed and configured **Active Directory Domain Services (AD DS)** on **Windows Server 2022**.  
Your server is now a **Domain Controller**, capable of managing:

- User and computer accounts
- Permissions and access control
- Group Policies and security settings

🚀 This setup forms the foundation for centralized identity and access management in an enterprise environment.

