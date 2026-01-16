# DNS Server on Windows Server 2022

This guide will help you install and configure a **DNS Server** on **Windows Server 2022**.

## Prerequisites

- A **Windows Server 2022** machine with **administrator privileges**.
- A static IP address for your server (recommended for DNS servers).
- A basic understanding of DNS concepts.

---

## Step 1: Install the DNS Server Role

1. Open **Server Manager** on your Windows Server 2022.
2. In the **Server Manager** window, click on **Manage** and select **Add Roles and Features**.
3. In the **Add Roles and Features Wizard**, click **Next** until you reach the **Select Server Roles** page.
4. On the **Select Server Roles** page, check the box for **DNS Server**.
5. Click **Next** and proceed through the wizard until you reach the **Confirm Installation Selections** page.
6. Click **Install** to begin the installation process.
---

## Step 2: Open DNS Manager

1. In **Server Manager**, click on **Tools** in the top right corner.

![1](https://github.com/pamxz/Windows-Server-Administration/blob/1f5a4b8eb7d433d2e8845861ed7a34ef49436f14/DNS/Screenshot%20(596).png)

3. Select **DNS** from the drop-down list to open the **DNS Manager**.

---

## Step 3: Configure the DNS Server

### 3.1: Set Up Forward Lookup Zones

A **forward lookup zone** allows the DNS server to resolve domain names to IP addresses.

1. In **DNS Manager**, right-click on **Forward Lookup Zones** and select **New Zone**.

![2](https://github.com/pamxz/Windows-Server-Administration/blob/1f5a4b8eb7d433d2e8845861ed7a34ef49436f14/DNS/Screenshot%20(597).png)


2. In the **New Zone Wizard**, click **Next**.
3. Select the **Primary zone** option and click **Next**.
4. On the next page, let the default option and click **Next**.

5. Enter the **Zone Name** (e.g., `example.com`), and click **Next**.

![3](https://github.com/pamxz/Windows-Server-Administration/blob/1f5a4b8eb7d433d2e8845861ed7a34ef49436f14/DNS/Screenshot%20(599).png)

6. Choose the **Do not allow dynamic updates** option (or select **Allow both non-secure and secure dynamic updates** if you want to enable dynamic updates), then click **Next**.
7. Click **Finish** to complete the zone creation.


![4](https://github.com/pamxz/Windows-Server-Administration/blob/1f5a4b8eb7d433d2e8845861ed7a34ef49436f14/DNS/Screenshot%20(602).png)


### 3.2: Add DNS Records

Now that the zone is created, you can add DNS records to map domain names to IP addresses.

1. In **DNS Manager**, right-click on the zone you just created and select **New Host (A or AAAA)**.
2. In the **New Host** window, enter the **Name** (e.g., `www` for `www.example.com`) and the corresponding **IP Address** (e.g., `192.168.1.100`).
3. Click **Add Host** to create the DNS record.

Repeat this process to add more records for other hostnames or services.

---

## Step 4: Configure Reverse Lookup Zones

### 4.1: Set Up Reverse Lookup Zones

A **reverse lookup zone** allows the DNS server to resolve IP addresses to domain names.

1. In **DNS Manager**, right-click on **Reverse Lookup Zones** and select **New Zone**.

![5](https://github.com/pamxz/Windows-Server-Administration/blob/1f5a4b8eb7d433d2e8845861ed7a34ef49436f14/DNS/Screenshot%20(603).png)


2. Follow the same steps as for forward lookup zones, but this time specify the **IP network** for which you want to create a reverse lookup zone (e.g., `192.168.10.x`).
3. Complete the wizard by clicking **Next** and **Finish**.

### 4.2: Set Up a pointer
A **pointer (PTR)** record is important because it maps an IP address back to a hostname, enabling reverse DNS lookups.

  1. Expand **Reverse Lookup Zones**.
  2. Right-click on the reverse lookup zone for the subnet of the IP address you want to add (e.g., `0.168.192.in-addr.arpa` for `192.168.10.x`) and then clic on **New Pointer (PTR)**.
  
![6](https://github.com/pamxz/Windows-Server-Administration/blob/1f5a4b8eb7d433d2e8845861ed7a34ef49436f14/DNS/Screenshot%20(604).png)


3. Enter the **IP Address** and **Hostname**:
   In the New Resource Record window, enter the IP address for the PTR record in the **Host IP Address** field.
   In the **Host name** field, enter the hostname that this IP address should map to (e.g., `server.example.com`).
4. Click **OK** to save the PTR record.
    
---

## Step 5: Test the DNS Server

### 5.1: Use nslookup to Test Forward Lookup

1. Open **Command Prompt** on any client machine in your network.
2. Type the following command:
   ```
   nslookup www.example.com
   ```
3. You should receive the corresponding IP address that you set in the DNS record.

### 5.2: Test Reverse Lookup

1. In **Command Prompt**, type the following command (replace `192.168.10.2` with an IP in your reverse zone):
   ```
   nslookup 192.168.10.2
   ```
2. You should receive the associated domain name for that IP address (e.g., `www.example.com`).

![7](https://github.com/pamxz/Windows-Server-Administration/blob/1f5a4b8eb7d433d2e8845861ed7a34ef49436f14/DNS/Screenshot%20(605).png)

---

