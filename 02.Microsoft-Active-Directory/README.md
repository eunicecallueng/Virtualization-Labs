This is a step-by-step documentation of how I successfully installed **Windows Server 2022** and configured **Active Directory (AD DS)** inside **VMware Workstation Pro**.

I wrote this guide to document my learning process and help fellow beginners who want to build their first IT lab for free!

---

## Prerequisites & Free Tools I Used

Before starting with Active Directory, you'll need to have your hypervisor ready and download the Windows Server ISO:

* **Hypervisor:** VMware Workstation Pro  
  *(If you haven't installed it yet, check out my other guide: [VMware Workstation Pro](Virtualization-Labs/01.VMware-Workstation-Pro/README.md)
* **Operating System:** [Windows Server 2022 ISO](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022) (Microsoft gives a free 180-day trial!)

---

Once I have successfully installed VMware Worstation Pro. I proceed to installing a windows Server 20222 ISO

---

## 💿 Step 2: Installing Windows Server

Installing the OS was pretty straightforward:

1. Booted into the setup and pressed any key to start.
2. Selected my preferred Language, Time, and Keyboard layout.
3. Clicked **Install Now**.
4. **Crucial Step:** Selected **Windows Server (Desktop Experience)** so I could get the full graphical desktop (GUI) instead of just a command prompt.
5. Selected **Custom: Install Windows only (advanced)** and picked the unallocated drive space.
6. Once installation completed, I set up a strong **Administrator Password**.

---

## ⚙️ Step 3: Preparing the Server (Before AD DS)

Before installing Active Directory, I learned that it's best practice to give the server a proper name and a static IP address:

1. **Renaming the Computer:**
   * Opened **Server Manager** > **Local Server**.
   * Clicked the default computer name (e.g., `WIN-123456`).
   * Renamed it to something readable: `DC01`, then restarted.

2. **Setting a Static IP:**
   * Pressed `Win + R`, typed `ncpa.cpl`, and hit **Enter**.
   * Right-clicked the network adapter > **Properties** > **IPv4**.
   * Manually assigned an IP address so the domain controller stays reachable:
     * **IP Address:** `192.168.10.10`
     * **Subnet Mask:** `255.255.255.0`
     * **Default Gateway:** `192.168.10.1`
     * **Preferred DNS:** `127.0.0.1` (points back to itself)

---

## 🏰 Step 4: Installing & Promoting Active Directory

This is where the magic happens!

### **A. Adding the AD DS Role**
1. In **Server Manager**, clicked **Add roles and features**.
2. Kept clicking **Next** until reaching **Server Roles**.
3. Checked **Active Directory Domain Services** (clicked *Add Features* when the popup appeared).
4. Clicked **Install** and waited for it to complete.

### **B. Promoting to Domain Controller**
1. Once installed, I clicked the **Yellow Notification Flag** at the top of Server Manager.
2. Selected **Promote this server to a domain controller**.
3. Chose **Add a new forest** (since this is my very first domain):
   * **Root domain name:** `lab.local`
4. Created a **DSRM Password** (used for emergency recovery).
5. Kept the rest as default and clicked **Install**.
6. The server automatically restarted to apply the changes!

---

## 🎉 Step 5: Testing & Verification

After the reboot, I logged in as `LAB\Administrator`. 

To verify everything worked:
* Opened **Server Manager** > **Tools**.
* Checked that **Active Directory Users and Computers**, **DNS**, and **Group Policy Management** were all available and active!

---

## 💭 What's Next?
Now that my primary Domain Controller is live, my next goal is to join a Windows 10/11 client machine to this domain and experiment with Group Policies (GPOs) and user account management. 

Feel free to star ⭐️ this repo if you're also on your IT learning journey!
