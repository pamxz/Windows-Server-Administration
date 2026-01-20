# Installation and Configuration Guide for FRSM on Windows Server

## 1. Introduction
File Server Resource Manager (FSRM) is a Windows Server role service used to control, monitor, and manage data stored on file servers. It allows administrators to configure disk quotas, file screening policies, and storage reports.

---

## 2. Prerequisites
- Windows Server 2019 or 2022
- Administrator privileges
- NTFS-formatted volume
- File Server role installed

---

## 3. Installing File Server Resource Manager (FSRM)

### 3.1 Installation Using Server Manager
1. Open **Server Manager**
2. Click **Add Roles and Features**
3. Select **Role-based or feature-based installation**
4. Choose the target server
5. Navigate to:  
   **File and Storage Services → File and iSCSI Services**
6. Select **File Server Resource Manager**
7. Click **Next → Install**

![1](https://github.com/pamxz/Windows-Server-Administration/blob/0bb9561e99cc3adad0923059cb9911e5cdaeafca/FRSM/Screenshot%20(620).png)

![2](https://github.com/pamxz/Windows-Server-Administration/blob/0bb9561e99cc3adad0923059cb9911e5cdaeafca/FRSM/Screenshot%20(621).png)

## Create a Quota

1. Open the **File Server Resource Manager (FSRM) Console**.
2. Expand **Quota Management**.
3. Right-click **Quotas** and select **Create Quota**.
4. Specify the folder path  
5. Select the quota type:
   - **Hard Quota** – Prevents users from exceeding the configured limit.
   - **Soft Quota** – Monitors disk usage without enforcing limits.
6. Choose one of the following:
   - Apply an existing **quota template**, or
   - Define a **custom quota limit**.
7. Click **Create** to apply the quota.
![3](https://github.com/pamxz/Windows-Server-Administration/blob/0bb9561e99cc3adad0923059cb9911e5cdaeafca/FRSM/Screenshot%20(622).png)

## 6. Configuring File Screening

### 6.1 Create a File Screen (GUI)

1. Open the **File Server Resource Manager (FSRM) Console**.
2. Expand **File Screening Management**.
3. Right-click **File Screens** and select **Create File Screen**.
4. Select the target folder where file screening will be applied.
5. Choose **Active Screening** to prevent users from saving blocked file types.
6. Apply an appropriate **file screen template**.
7. Click **Create** to enforce the file screening policy.
   
![4](https://github.com/pamxz/Windows-Server-Administration/blob/0bb9561e99cc3adad0923059cb9911e5cdaeafca/FRSM/Screenshot%20(624).png)

---

### 6.2 Create a Custom File Group

1. In the FSRM Console, expand **File Screening Management**.
2. Click **File Groups**.
3. Right-click **File Groups** and select **Create File Group**.
4. Enter a **File group name** (e.g., `Blocked Executables`).
5. Specify the **file extensions or patterns** to block (e.g., `*.exe`, `*.bat`, `*.cmd`, `*.ps1`).
6. Save the file group for use in file screen templates or direct file screens.

![5](https://github.com/pamxz/Windows-Server-Administration/blob/0bb9561e99cc3adad0923059cb9911e5cdaeafca/FRSM/Screenshot%20(625).png)



