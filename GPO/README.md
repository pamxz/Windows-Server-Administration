# Create Group Policy Objects (GPOs) on Windows Server

This guide provides a step-by-step process for **creating Group Policy Objects (GPOs)** on **Windows Server **. GPOs are used to manage and configure operating system settings, security options, and applications across a network.

## Prerequisites

- A **Windows Server ** machine with **administrator privileges**.
- An **AD DS** role installed and configured.
- Familiarity with **Active Directory** and **Group Policy** concepts.

---

## Step 1: Open the Group Policy Management Console (GPMC) 

The **Group Policy Management Console (GPMC)** is the central tool for creating and managing GPOs.

1. **Open Server Manager**:
   - Click the **Start** button and open **Server Manager**.

2. **Install the Group Policy Management Feature (if not already installed)**:
   - In **Server Manager**, click **Add roles and features**.
   - Select **Role-based or feature-based installation**, then click **Next**.
   - On the **Select features** page, check the box next to **Group Policy Management**.
   - Click **Next**, and then **Install** if it's not already installed.

3. **Open GPMC**:
   - After installation, click the **Start** button, type **Group Policy Management**, and press **Enter**.
   - This will open the **Group Policy Management Console**.

![1](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(606).png)

---

## Step 2: Create a New Group Policy Object (GPO)

Once the GPMC is open, you can create a new GPO.

1. **Navigate to the Domain**:
   - In **Group Policy Management**, expand the forest and domain nodes in the left pane to locate your domain.

2. **Create a New GPO**:
   - Right-click on the **Group Policy Objects** node under your domain and select **New**.


![2](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(607).png)


   - Enter a **name** for the GPO (e.g., **Custom Security Settings**).
   - Click **OK** to create the new GPO.


![3](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(608).png)

---

## Step 3: Edit the GPO

After creating the GPO, you need to edit it to apply specific settings.

1. **Right-click the GPO**:
   - Right-click the newly created GPO and select **Edit**.


![4](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(609).png)


2. **Configure the Settings**:
   - The **Group Policy Management Editor** will open. This editor allows you to configure both **Computer Configuration** and **User Configuration** settings.
     - **Computer Configuration**: Settings that apply to computers (e.g., security settings, software installation).
     - **User Configuration**: Settings that apply to user accounts (e.g., desktop settings, folder redirection).
   - Navigate through the sections in the **Editor** and configure the settings you require. For example:
     - **Security Settings**: Under **`Computer Configuration > Policies > Windows Settings > Security Settings>Account Policies>Password Policy`**, you can configure password policies, user rights assignments, etc.
  
   ![5](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(611).png)

   
3. **Apply the Changes**:
   - After configuring the desired settings, close the **Group Policy Management Editor**.

---

## Step 4: Link the GPO to an Organizational Unit (OU) or Domain

Now that the GPO is created and configured, you need to apply it by linking it to an **Organizational Unit (OU)** or the entire **domain**.

1. **Link the GPO**:
   - In the **Group Policy Management Console**, right-click on the **OU** or **domain** where you want the GPO to apply.
   - Select **Link an Existing GPO**.


![6](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(612).png)


2. **Select the GPO**:
   - In the **Select GPO** dialog, select the GPO you created (e.g., **Custom Security Settings**) and click **OK**.


![7](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(613).png)


---

## Step 5: Force Group Policy Update

To apply the new GPO immediately, you can force a group policy update on the client machines.

1. **Force Update on the Server**:
   - Open **Command Prompt** on the server and type the following command:
     ```bash
     gpupdate /force
     ```


![8](https://github.com/pamxz/Windows-Server-Administration/blob/09cae7dfd5827243a00f4b62c534e6aeb0738d8f/GPO/Screenshot%20(614).png)


2. **Force Update on Client Machines**:
   - On client machines, open **Command Prompt** and type the following command:
     ```bash
     gpupdate /force
     ```

This will immediately apply the new policy settings.

---


## Additional Notes

- **GPO Precedence**: If multiple GPOs are linked to an OU, the order in which they are applied is determined by the link order. You can adjust this order in the **Group Policy Management Console** by using the **Up** and **Down** buttons in the **Linked Group Policy Objects** section.
- **GPO Inheritance**: By default, GPOs are inherited from parent OUs to child OUs. You can block inheritance at a specific level if needed by right-clicking on an OU and selecting **Block Inheritance**.

---

