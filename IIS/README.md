# Installation and Set Up of IIS on Windows Server

This guide walks you through the steps to **install** and **set up** **IIS (Internet Information Services)** on **Windows Server**.

## Prerequisites

- A **Windows Server** machine with **administrator privileges**.
- A basic understanding of **web servers** and **IIS**.

---

## Step 1: Install IIS (Internet Information Services)

1. **Open Server Manager**:
   - Click the **Start** button and open **Server Manager**.

2. **Add Roles and Features**:
   - In **Server Manager**, click **Manage** in the top-right corner and then select **Add Roles and Features**.

3. **Start the Wizard**:
   - The **Add Roles and Features Wizard** will open. Click **Next** to proceed.

4. **Select Installation Type**:
   - In the **Installation Type** section, select **Role-based or feature-based installation** and click **Next**.

5. **Select the Destination Server**:
   - Choose the server on which you want to install IIS (the local server is selected by default). Click **Next**.

6. **Select Server Roles**:
   - In the **Select server roles** section, check **Web Server (IIS)**.
   - A prompt will appear to install additional features required for IIS. Click **Add Features**.
   - Click **Next**.


![1](https://github.com/pamxz/Windows-Server-Administration/blob/637be2248d5a8a4ceebbe341a507f2c3fb31dad1/IIS/Screenshot%20(615).png)


7. **Select Features**:
   - In the **Select features** section, you can add additional features, but the default selection for **Web Server (IIS)** is sufficient for most use cases. Click **Next**.

8. **Select Role Services**:
   - In the **Select role services** section, you can choose specific IIS services you want to install. The default options are generally sufficient. For a basic IIS installation, leave the default selections and click **Next**.

![2](https://github.com/pamxz/Windows-Server-Administration/blob/637be2248d5a8a4ceebbe341a507f2c3fb31dad1/IIS/Screenshot%20(616).png)

9. **Confirm Installation**:
   - Review your selections and click **Install** to start the installation process.
   - The installation may take a few minutes to complete.
  
![3](https://github.com/pamxz/Windows-Server-Administration/blob/637be2248d5a8a4ceebbe341a507f2c3fb31dad1/IIS/Screenshot%20(617).png)

10. **Complete the Installation**:
    - Once the installation is complete, click **Close**.
---

## Step 2: Verify IIS Installation

1. **Open IIS Manager**:
   - To confirm IIS was installed successfully, click the **Start** button and search for **IIS Manager**.
   - Open the **Internet Information Services (IIS) Manager** application.

2. **Verify IIS Server is Running**:
   - In **IIS Manager**, under **Connections**, you should see your server name listed. This confirms that IIS is installed and running.


![4](https://github.com/pamxz/Windows-Server-Administration/blob/637be2248d5a8a4ceebbe341a507f2c3fb31dad1/IIS/Screenshot%20(618).png)

3. **Test IIS**:
   - Open a web browser and type `http://localhost` in the address bar. You should see the **IIS Welcome Page**, which confirms that the web server is up and running.


![5](https://github.com/pamxz/Windows-Server-Administration/blob/637be2248d5a8a4ceebbe341a507f2c3fb31dad1/IIS/Screenshot%20(619).png)

---
## Step 3: Configure Firewall (Optional)

If you need to allow access to your IIS server from other computers, ensure that the **Windows Firewall** allows HTTP and HTTPS traffic.

1. **Open Windows Defender Firewall**:
   - Go to **Control Panel** > **System and Security** > **Windows Defender Firewall**.

2. **Allow an App or Feature**:
   - On the left-hand side, click **Allow an app or feature through Windows Defender Firewall**.

3. **Enable Web Traffic**:
   - Scroll down and ensure that **World Wide Web Services (HTTP)** and **World Wide Web Services (HTTPS)** are allowed through both private and public networks.
   - Click **OK** to save the changes.

---

## Step 4: Monitor IIS (Optional)

You can use **IIS Manager** to monitor the status of your server and websites:

1. **Check Site Health**:
   - In **IIS Manager**, you can see the status of all your sites under **Sites**. Ensure that the **Status** is set to **Started**.

2. **Check Logs**:
   - IIS keeps logs of all requests made to your server. To check these logs, navigate to the **Logging** section under the site’s settings in **IIS Manager**.
   - You can view, filter, and analyze the logs to troubleshoot or monitor activity.

---

## Additional Notes

- **IIS Features**: IIS comes with many additional features that can be enabled based on your needs, including SSL encryption, authentication, URL rewriting, and more.
- **Permissions**: Be sure to set proper permissions for files and directories to ensure your websites are secure.
- **Website Content**: Ensure that the website content is properly configured, and test the website regularly to ensure uptime and accessibility.

---
