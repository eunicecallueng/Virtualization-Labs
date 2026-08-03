This is a step-by-step documentation of how I successfully installed **Windows Server 2022** and configured **Active Directory (AD DS)** inside **VMware Workstation Pro**.

I wrote this guide to document my learning process and help fellow beginners who want to build their first IT lab for free!

---

## Prerequisites & Free Tools I Used

Before starting with Active Directory, you'll need to have your hypervisor ready and download the Windows Server ISO:

* **Hypervisor:** VMware Workstation Pro  
  *(If you haven't installed it yet, check out my other guide: [VMware Workstation Pro](https://github.com/eunicecallueng/Virtualization-Labs/blob/main/01.VMware-Workstation-Pro/README.md)
* **Operating System:** [Windows Server 2022 ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022) (Microsoft gives a free 180-day trial!)

---

## 💿 Step 1: Installing Windows Server 2022

1. Launch **VMware Workstation Pro** and create a new Virtual Machine attaching the downloaded Windows Server 2022 ISO.
2. Boot into the installer and press any key when prompted.
3. Select your preferred **Language**, **Time**, and **Keyboard Layout**, then click **Install Now**.
4. ⚠️ **Crucial Step:** Select **Windows Server 2022 Datacenter (Desktop Experience)** or **Standard (Desktop Experience)** to ensure you get the full Graphical User Interface (GUI).
5. Select **Custom: Install Windows only (advanced)** and choose your unallocated partition.
6. Set a strong local **Administrator Password** upon first startup.

---

## ⚙️ Step 2: Preparing the Server

Best practice requires assigning a proper hostname and a static IP address before promoting to a Domain Controller.

### 1. Rename the Computer
1. Open **Server Manager** > **Local Server**.
2. Click the default computer name (e.g., `WIN-123456`).
3. Change the computer name to `DC01` and restart the virtual machine.

### 2. Configure Static IP Address
1. Press `Win + R`, type `ncpa.cpl`, and hit **Enter**.
2. Right-click your network adapter > **Properties** > **Internet Protocol Version 4 (TCP/IPv4)**.
3. Apply the following settings:

| Parameter | Value |
| :--- | :--- |
| **IP Address** | `192.168.10.10` |
| **Subnet Mask** | `255.255.255.0` |
| **Default Gateway** | `192.168.10.1` |
| **Preferred DNS** | `127.0.0.1` *(Loopback to self)* |

---

## 🏰 Step 3: Installing & Promoting AD DS

### Phase A: Adding the AD DS Role
1. In **Server Manager**, click **Manage** > **Add Roles and Features**.
2. Progress through the wizard until reaching **Server Roles**.
3. Check **Active Directory Domain Services** (click **Add Features** on the pop-up).
4. Click **Install** and wait for completion.

### Phase B: Promoting to Domain Controller
1. Click the **Yellow Notification Flag** in Server Manager.
2. Select **Promote this server to a domain controller**.
3. Choose **Add a new forest** and enter your domain name:
   * **Root Domain Name:** `lab.local`
4. Set a strong **DSRM (Directory Services Restore Mode) Password**.
5. Leave remaining options at default and click **Install**. The server will automatically reboot.

---

## 🎉 Step 4: Testing & Verification

1. Log into the server using domain administrator credentials: `LAB\Administrator`.
2. Open **Server Manager** > **Tools**.
3. Verify the following tools are present and functional:
   - [x] Active Directory Users and Computers
   - [x] DNS Manager
   - [x] Group Policy Management

Feel free to star ⭐️ this repo if you're also on your IT learning journey!
