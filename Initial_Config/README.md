# Server Administration

This documentation provides a straightforward guide to installing and configuring essential
Windows Server roles and features for managing users and computers within a network
environment.

---

## Prerequisites

Before proceeding with the installation and configuration steps, ensure your host machine meets
the following minimum requirements:

- **Processor**: 1.4 GHz 64-bit processor with virtualization enabled
- **Memory**: 2 GB RAM (4 GB and above is recommended for optimal performance)
- **Storage**: 32 GB of available disk space
- **Network**: Ethernet adapter of 1 Gbps
- **Virtualization Software**:
  - Hyper-V (Windows), or
  - VMware Workstation / VirtualBox (pre-installed)
- **Windows Server ISO**:
  - Windows Server `.iso` image from Microsoft’s website
  - Valid license or bootable installation media

---

## Step 1: Create a New Virtual Machine

1. Open **VMware Workstation**
2. Click **Create a New Virtual Machine**
3. Choose:
   - **Typical (recommended)** → Click **Next**

4. Select:
   - **Installer disc image file (ISO)**
   - Browse and select your **Windows Server 2022 ISO**

   ![vm](Screenshot%20(143).png)

5. Add a **license key** (if available) and select the appropriate **Windows Server edition**
   based on your requirements, then click **Next**

---

### 6. Name the Virtual Machine

- Enter a name (e.g., **WindowsServer2022**)
- Choose a location to store the virtual machine files
- Click **Next**

---

### 7. Specify Disk Capacity

- Set disk size (e.g., **60 GB or more**, depending on requirements)
- Select **Store virtual disk as a single file** (better performance)
- Click **Next**

---

### 8. Customize Hardware (Optional but Recommended)

- Click **Customize Hardware**
- Configure the following:
  - **Memory**: 4 GB minimum (8 GB or more recommended)
  - **Processors**: At least 2 cores
  - **Network Adapter**: NAT or Bridged (depending on whether the server should be accessible on the local network)
- Click **Finish** when done

---

### 9. Finish Setup

- Click **Finish**
- The virtual machine will now appear in your VM list
- Allow the installation process to complete and restart when prompted

---

## Step 2: Initial Configuration

### 1. Rename the Computer

- Open **Server Manager**
- Navigate to **Local Server**
- Click on the **Computer Name**
- In **System Properties**, click **Change**
- Enter a new computer name and restart the server when prompted

---

### 2. Set a Static IP Address

1. Open **Server Manager** → **Local Server**
2. Click the **IPv4 address** link next to your network adapter
3. In **Network Connections**, right-click the adapter → **Properties**
4. Select **Internet Protocol Version 4 (TCP/IPv4)** → **Properties**
5. Configure:
   - Static IP address
   - Subnet mask
   - Default gateway
   - DNS server(s)

> Use a properly allocated subnet specific to the server environment.

---

## Setting Administrator Account

An **Administrator account** on a Windows Server (or any Windows system) is a user account with
full system privileges. It has the highest level of access, allowing it to:

- Install and uninstall software or Windows features
- Create, modify, or delete user accounts
- Change system-wide settings
- Access all files and folders
- Configure security policies and firewall rules
- Perform server roles such as Active Directory, DNS, and DHCP configuration

> The Administrator account is **disabled by default** and must be configured before performing
administrative tasks.

---

### Steps to Configure the Administrator Account

1. Open **Server Manager**
   - Click **Start** → **Server Manager** (it may launch automatically)

2. Open **Control Panel**
   - Select **User Accounts**
   - Click **Manage another account**
   - Select the **Administrator** account
   - Configure and set a secure **Administrator password**
