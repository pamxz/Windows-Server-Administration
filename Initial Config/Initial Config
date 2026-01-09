**Prerequisites Check**

Before proceeding with the installation and configuration steps, ensure your host machine meets
the following minimum requirements:

Processor: 1.4 GHz 64-bit processor virtualization enabled

Memory: 2 **GB** RAM (4 GB and above is recommended for optimal performance)

Storage 32 GB of storage space

Network Ethernet Adapter of 1GBps

Virtualization Software such as Hyper-V (windows) or other application software such as VMware
Workstation or Virtual Box pre-installed

Windows Server Disk .iso image from Microsoft’s website or bootable media with licenses

**Step 1: Create a New Virtual Machine**

1. Open **VMware Workstation**
2. Click on **"Create a New Virtual Machine"**
3. Choose:
    o **Typical (recommended)** → Next


4. Select: **Installer disc image file (iso)** → Browse to your Windows Server 2022.iso


5. Add Licensing key (if its available) and select the version of windows server to be installed
    based on requirements. Click Next


**6. Name the Virtual Machine**
    o Enter a name (e.g., WindowsServer2022)
    o Choose a location to store the VM files
    o Click **Next
7. Specify Disk Capacity**
    o Set disk size (e.g., **60 GB or more** , depending on requirements)
    o Select **Store virtual disk as a single file** (better performance)
    o Click **Next
8. Customize Hardware (Optional but Recommended)**
    o Click **Customize Hardware** :
    o **Memory** : 4 GB minimum (8 GB or more recommended)
    o **Processors** : At least 2 cores
    o **Network Adapter** : Set to NAT or Bridged (depending on whether you want it to be
       accessible on the local network)
    o Click **Finish** when done


**9. Finish Setup**
    o Click **Finish**
    o The VM will now appear in your VM list, wait a while for the installation to finish and
       restart

**Step 2: Initial Configuration**

**1. Rename the Computer**
o In Server Manager → Local Server → Click on the **Computer name**.
o In **System Properties** , click **Change...**.
o Enter a new computer name and restart when prompted.


**Set a Static IP Address**

1. Open Server Manager → Local Server.
2. Click the **IPv4 address** link next to your network adapter.
3. In **Network Connections** , right-click the adapter → Properties.
4. Select **Internet Protocol Version 4 (TCP/IPv4)** → Properties.


5. Set a static IP, subnet mask, gateway, and DNS server(s). Using a speficied subnet allocated
    for the server

## SETTING ADMINISTRATOR ACCOUNT

An Administrator account on a Windows Server (or any Windows system) is a user account with full
system privileges. It has the highest level of access, allowing it to:

- Install and uninstall software or Windows features
- Create, modify, or delete user accounts
- Change system-wide settings
- Access all files and folders, even those owned by other users
- Configure security policies and firewall rules
- Perform server roles like setting up Active Directory, DNS, DHCP, etc.

Administrator account is disabled by default and need to configured to perform specific tasks

The following are steps to configure admin account:

1. **Open Server Manager**
- Click Start, then Server Manager (or it may launch automatically on login).


- Open Control Panel and Select User Account
- Select Manage another Account
- Select the Administrator Account and configure Administrator Password

