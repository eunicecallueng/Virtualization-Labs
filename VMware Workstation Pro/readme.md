# VMware Workstation Pro Installation Lab

## Why Install VMware First?

I chose to install **VMware Workstation Pro** before setting up GNS3 because it acts as the ***base virtualization platform*** for all my labs.  
The reason is that during GNS3 setup, it will detect VMware and make configuration easier. If I install GNS3 first and VMware later, I might need to reconfigure some settings manually — which is extra work I’d rather avoid.  

By installing VMware first, I make sure my environment is ready and smooth for the next steps.


---

## Why VMware Workstation Pro?
- Reliable virtualization platform for running multiple VMs.  
- Easy integration with networking labs (like GNS3).  
- Good balance of performance and usability for practice environments.  


---

## Pre‑Installation (Windows Host)

First things first — before installing **VMware Workstation Pro** or any kind of virtualization base, you have to make sure you computer has **virtualization enabled**.  

Since I’m using **Windows OS**, here’s what I did:

1. Pressed **Ctrl + Shift + Esc** to open Task Manager → went to the **Performance tab → CPU** to check if Virtualization was Enabled.  
   - In my case, it was already enabled (you can see it under CPU details).
      ![CPU details showing Virtualization Enabled](CPU-details.jpeg)


But just in case it’s disabled, you’ll need to enable it via BIOS/UEFI.

1.. Restart your  PC and pressed the BIOS/UEFI access key repeatedly during boot (commonly **F2, F10, F12, Delete, or Esc**, depending on the manufacturer).  

3. Alternatively, I tested the Windows method: **Hold Shift while selecting Restart → Troubleshoot → Advanced options → UEFI Firmware Settings → Restart.**

4. Inside BIOS/UEFI, I navigated to the **Advanced / CPU Configuration** section.  
   - For Intel CPUs: enabled **Intel Virtualization Technology (VT‑x)**.  
   - For AMD CPUs: enabled **SVM Mode**.  

5. Saved changes and exited BIOS/UEFI (usually by pressing **F10** and confirming).  

6. After reboot, I opened Task Manager again and confirmed **Virtualization: Enabled** under the Performance tab.  

With virtualization enabled, I was ready to proceed with installing VMware Workstation Pro.



## Installation Steps

### 1. Download Installer
- Go to the official VMware website.  
- Download the latest **VMware Workstation Pro** installer for Windows.  

### 2. Run Installer
- Double-click the `.exe` file.  
- Follow the wizard prompts:  
  - Accept license agreement  
  - Choose installation directory (default is fine)  
  - Enable Enhanced Keyboard Driver if needed  

### 3. License Key
- Enter a valid license key (or use trial mode for practice).  

### 4. Finish Setup
- Complete installation and restart your PC if prompted.  

---

## 🔧 Post-Installation Setup

### Create Your First VM
1. Open **VMware Workstation Pro**.  
2. Click **Create a New Virtual Machine**.  
3. Choose **Typical (recommended)**.  
4. Select your ISO file (e.g., Ubuntu Server).  
5. Configure VM settings (RAM, CPU, disk size).  
6. Finish and power on the VM.  

---

## 📓 Notes
This lab is for **practice documentation only**.  
I’m using it to:  
- Learn how to set up virtualization environments.  
- Prepare a base VM for my other labs (GNS3, Wireshark, Zabbix).  
- Share reproducible steps for anyone following along.  

---

## 🚀 Next
- After VMware is installed, proceed to create Ubuntu VMs for Zabbix and Wireshark.  
- Document each lab in its own subfolder.  
