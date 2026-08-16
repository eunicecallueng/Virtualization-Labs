## 🖥️ On-Premises Active Directory Configuration & Exercises

A comprehensive implementation of **Active Directory Domain Services (AD DS)** on Windows Server, covering core infrastructure services, OU architecture, security management, and Group Policy enforcement.

### 📚 Laboratory Modules

| # | Exercise Title | Description | Demo / Media |
|---|---|---|---|
| **01** | **AD DS Installation & Forest Promotion** | Promoted server as Primary Domain Controller for `nycehomelab.local`. | [Read details](https://github.com/eunicecallueng/Virtualization-Labs/blob/main/02.Microsoft-Active-Directory/Configuring%20Active%20Directory/README.md)
| **02** | **DNS & Network Services** | Configured Active Directory-Integrated Forward/Reverse Lookup Zones. | [Watch Demo](./media/02-dns-config.gif) |
| **03** | **DHCP Server Deployment** | Authorized DHCP server and set up dynamic IP allocation scope. | [Watch Demo](./media/03-dhcp-setup.gif) |
| **04** | **OU Architecture Design** | Designed `Nyce_Users` and `Workstations` organizational units. | [Watch Demo](./media/04-ou-design.gif) |
| **05** | **Departmental Sub-OUs** | Segmented users into `BPO_Roles`, `HR_Department`, and `IT_Department`. | [Watch Demo](./media/05-sub-ous.gif) |
| **06** | **User Account Provisioning** | Created UPN-configured domain accounts (`jordan.reed`). | [Watch Demo](./media/06-user-provision.gif) |
| **07** | **Security Groups & RBAC** | Built Global and Domain Local security groups for permission control. | [Watch Demo](./media/07-rbac-groups.gif) |
| **08** | **Domain Joining Workstations** | Joined Windows 10/11 client VMs to `nycehomelab.local`. | [Watch Demo](./media/08-domain-join.gif) |
| **09** | **Domain Password Policy** | Enforced complexity and lockout thresholds via `gpmc.msc`. | [Watch Demo](./media/09-password-policy.gif) |
| **10** | **Fine-Grained Password Policies** | Configured Password Settings Objects (PSOs) for IT admins. | [Watch Demo](./media/10-fgpp-pso.gif) |
| **11** | **GPO: Network Drive Mapping** | Automated company drive mapping based on department membership. | [Watch Demo](./media/11-drive-mapping.gif) |
| **12** | **GPO: Control Panel Restriction** | Restricted non-admin access to system settings applets. | [Watch Demo](./media/12-prohibit-cp.gif) |
| **13** | **GPO: USB Storage Blocking** | Disabled unauthorized USB removable media read/write access. | [Watch Demo](./media/13-usb-block.gif) |
| **14** | **GPO: User Account Control** | Enforced mandatory secure desktop prompts for admin elevation. | [Watch Demo](./media/14-enforce-uac.gif) |
| **15** | **GPO: Inactivity Screen Lock** | Configured automated screen lock timeouts on idle sessions. | [Watch Demo](./media/15-screen-lock.gif) |
| **16** | **GPO: WSUS Patch Management** | Directed endpoint patching schedules to internal WSUS server. | [Watch Demo](./media/16-wsus-update.gif) |
