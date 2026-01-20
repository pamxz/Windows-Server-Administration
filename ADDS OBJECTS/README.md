# Users in Active Directory on Windows Server 2022

This guide provides step-by-step instructions on how to add users in **Active Directory (AD)** on **Windows Server 2022**.

---
## Prerequisites

- Windows Server 2022 with **Active Directory Domain Services (AD DS)** installed  
- Administrator privileges to manage users in Active Directory  
---
## Step 1: Open Active Directory Users and Computers

### Access AD DS
- In **Server Manager**, click **Tools** (top-right corner)
- Select **Active Directory Users and Computers**

![1](https://github.com/pamxz/Windows-Server-Administration/blob/b564f841315edadea073c25aa5dc8ca613eb8c8a/ADDS%20OBJECTS/Screenshot%20(628).png)

## Step 2: Navigate to the Organizational Unit (OU)

- In **Active Directory Users and Computers**, locate the **Organizational Unit (OU)** where you want to create the user
- By default, users can be created in the **Users** container
- You may also create custom OUs (e.g., *Employees*, *IT Department*, etc.)

### Create a New User
- Right-click the target OU (e.g., **Users**)
- Select **New > User**

![2](https://github.com/pamxz/Windows-Server-Administration/blob/b564f841315edadea073c25aa5dc8ca613eb8c8a/ADDS%20OBJECTS/Screenshot%20(630).png)

## Step 3: Create a New User Account

### Enter User Details
In the **New Object – User** dialog, fill in the following:

- **First name**: User’s first name  
- **Initials** (optional): User’s initials  
- **Last name**: User’s last name  
- **Full name**: Auto-populated (editable if needed)  
- **User logon name**: Username for login (e.g., `jdoe`)  

Click **Next** to continue.

![3](https://github.com/pamxz/Windows-Server-Administration/blob/b564f841315edadea073c25aa5dc8ca613eb8c8a/ADDS%20OBJECTS/Screenshot%20(631).png)

---

### Set Password

- Enter a password in the **Password** and **Confirm password** fields
- Select appropriate password options:
  - **User must change password at next logon** *(recommended)*
  - **User cannot change password**
  - **Password never expires**
  - **Account is disabled** *(useful for staging accounts)*

Click **Next**.

![4](https://github.com/pamxz/Windows-Server-Administration/blob/b564f841315edadea073c25aa5dc8ca613eb8c8a/ADDS%20OBJECTS/Screenshot%20(632).png)

### Finish

- Review the configuration details
- Click **Finish** to create the user account
---

## Notes (Best Practice)

- Always use **Organizational Units (OUs)** instead of the default *Users* container
- Enforce **password policies via Group Policy**
- Avoid setting **Password never expires** for standard users
- Use **least privilege** when assigning group memberships

---

# How to Create Groups on Windows Server 2022

This guide walks you through the steps to create groups on **Windows Server 2022**.  
Groups are essential for organizing users and efficiently assigning permissions.

---

## Step 1: Open Active Directory Users and Computers

To create groups, you need to access the **Active Directory Users and Computers (ADUC)** console.

### Open Server Manager
- Click the **Start** button
- Open **Server Manager**

### Access Active Directory Users and Computers
- In **Server Manager**, click **Tools** (top-right corner)
- Select **Active Directory Users and Computers** from the dropdown

---

## Step 2: Create a New Group

Once inside the **Active Directory Users and Computers** console, follow these steps:

### Navigate to the Organizational Unit (OU)
- Locate the **Organizational Unit (OU)** (e.g., `Finance`) where you want to create the group
- Right-click the OU and select **New > Group**
---
### Enter Group Information

In the **New Object – Group** window, configure the following:

- **Group name**: Enter the name of the group (e.g., `HR_Department`)
- **Group name (pre-Windows 2000)**: Auto-filled (can be modified if needed)
- **Group scope**:
  - **Domain Local** – Used for permissions within the same domain
  - **Global** – Used for assigning permissions within the domain
  - **Universal** – Used for permissions across multiple domains
- **Group type**:
  - **Security** – Used to assign permissions *(recommended for access control)*

Click **OK** to create the group.

![3](https://github.com/pamxz/Windows-Server-Administration/blob/b564f841315edadea073c25aa5dc8ca613eb8c8a/ADDS%20OBJECTS/Screenshot%20(634).png)

---

## Step 3: Add Members to the Group

After creating the group, add users or other groups as members.

### Select the Group
- Navigate to the group you just created in **Active Directory Users and Computers**

### Open Group Properties
- Right-click the group
- Select **Properties**
---

### Add Members
- In the **Group Properties** window, go to the **Members** tab
- Click **Add**
- Enter the names of users or groups to add
- Click **OK**

![5](https://github.com/pamxz/Windows-Server-Administration/blob/b564f841315edadea073c25aa5dc8ca613eb8c8a/ADDS%20OBJECTS/Screenshot%20(636).png)

---

### Save Changes
- Click **Apply**
- Click **OK** to save the configuration

---
# How to Create Organizational Units (OUs) on Windows Server 2022

This guide walks you through the steps to create **Organizational Units (OUs)** on **Windows Server 2022** using the **Active Directory Users and Computers (ADUC)** tool.

---
## Step 1: Open Active Directory Users and Computers (ADUC)
### Open Server Manager
- Click the **Start** button
- Open **Server Manager**

### Launch ADUC
- In **Server Manager**, click **Tools** (top-right corner)
- Select **Active Directory Users and Computers** from the dropdown  
  This opens the ADUC management console

![6](https://github.com/pamxz/Windows-Server-Administration/blob/b564f841315edadea073c25aa5dc8ca613eb8c8a/ADDS%20OBJECTS/Screenshot%20(637).png)

---

## Step 2: Navigate to the Domain

### Expand the Domain
- In the **ADUC** console, locate your domain under **Active Directory Users and Computers**
- Click the arrow next to your domain name to expand it
- You will see default containers such as:
  - **Users**
  - **Computers**
  - **Domain Controllers**

## Step 3: Create the Organizational Unit (OU)

### Define the OU Name
- In the **New Object – Organizational Unit** window:
  - Enter the **OU name** (e.g., `Finance`, `HR`, `Sales`)
  - Optionally add a **description**

### Set Permissions (Optional)
- Check **Protect object from accidental deletion** *(recommended)*

Click **OK** to create the OU.

![7](https://github.com/pamxz/Windows-Server-Administration/blob/044a5432f76591bd20e12ffa99e6e9a451145896/ADDS%20OBJECTS/Screenshot%20(638).png)

---
## Step 4: Verify the OU Creation

### Check the New OU
- Expand your domain or parent container
- Confirm the new OU appears in the list

### View OU Properties
- Right-click the new OU
- Select **Properties**
- Modify settings such as:
  - Delegation of control
  - Security permissions
  - Object management options

---

## Best Practices

- Design OUs based on **administrative boundaries**, not departments alone
- Always enable **protection from accidental deletion**
- Apply **Group Policy Objects (GPOs)** at the OU level
- Avoid excessive OU nesting
- Use clear, consistent naming conventions

---


---

