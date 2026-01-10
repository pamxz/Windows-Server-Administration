# How to Set Up Active Directory Domain Services (AD DS) on Windows Server 2022

This guide provides step-by-step instructions for installing and configuring **Active Directory Domain Services (AD DS)** on **Windows Server 2022**. AD DS enables you to create and manage a domain, centralizing user and computer management within a network.

---

## Prerequisites

Before you begin, ensure the following requirements are met:

- **Administrator privileges**
- A **static IP address** configured on the server  
  *(Check the Inital Config file to make necessary settings)*
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

> 📸[1](https://github.com/pamxz/Windows-Server-Administration/blob/866ac42d5f8524e9abe038793ab2969354683ad5/ADDS/Screenshot%20(572).png)

### 3. Select Installation Type
- Choose **Role-based or feature-based installation**
- Click **Next**

> 📸 [2](https://github.com/pamxz/Windows-Server-Administration/blob/866ac42d5f8524e9abe038793ab2969354683ad5/ADDS/Screenshot%20(573).png)

### 4. Select Destination Server
- Ensure the current server is selected
- Click **Next**

### 5. Select Server Roles
- Check **Active Directory Domain Services**
- When prompted, click **Add Features**

> 📸 [3](https://github.com/pamxz/Windows-Server-Administration/blob/866ac42d5f8524e9abe038793ab2969354683ad5/ADDS/Screenshot%20(2172).png)

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

> 📸 

⏳ The installation may take a few minutes.  
⚠️ **Do not close the wizard** — you will need it to promote the server to a domain controller.

---

## Step 2: Promote the Server to a Domain Controller

### 1. Promote to Domain Controller
- Click **Promote this server to a domain controller**

> 📸 [4](https://github.com/pamxz/Windows-Server-Administration/blob/866ac42d5f8524e9abe038793ab2969354683ad5/ADDS/Screenshot%20(575).png)

### 2. Deployment Configuration
- Select **Add a new forest**
- Enter your **Root domain name** (e.g., `example.com`)
- Click **Next**

> 📸 [5](https://github.com/pamxz/Windows-Server-Administration/blob/866ac42d5f8524e9abe038793ab2969354683ad5/ADDS/Screenshot%20(576).png)

### 3. Domain Controller Options
- Set **Forest functional level** and **Domain functional level**  
  *(Default: Windows Server 2022)*
- Ensure **DNS server** is checked
- Enter a **Directory Services Restore Mode (DSRM)** password
- Click **Next**

> 📸 [6](https://github.com/pamxz/Windows-Server-Administration/blob/866ac42d5f8524e9abe038793ab2969354683ad5/ADDS/Screenshot%20(2242).png)

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

> 📸 [7](https://github.com/pamxz/Windows-Server-Administration/blob/866ac42d5f8524e9abe038793ab2969354683ad5/ADDS/Screenshot%20(577).png)

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

