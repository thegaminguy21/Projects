# Active Directory Setup on Windows Server 2022  
**Goal**: Deploy a functional AD Domain Controller with users, OUs, and Group Policies.  

## **Steps**  
1. **Installed Windows Server 2022 via Hyper-V  
   - Used Hyper-V to Install SERVER_EVAL_x64FRE_en-us.ISO
   - Installed Windows Server 2022 Datacenter Evaluation (Desktop Experience) x64

2. **General Setup Procedures**
   - Checked for Windows Updates
   - Set and changed Time Zone
   - Assigned static IP Address (192.168.199.100/24) Gateway: 192.168.199.1
   - Enable Remote Desktop on Server
   - Rename Server Win22-DC01
   - Rebooted the Server and tested and checked new configurations
     
3. **Created Organizational Units (OUs)**  
   - `Employees`, `Admins`, `Servers` with hierarchical structure.  
4. **Automated User Creation**  
   - Used PowerShell:  
     ```powershell
     New-ADUser -Name "John Doe" -SamAccountName jdoe -Path "OU=Employees,DC=lab,DC=local"  
     ```  
5. **Configured Group Policy**  
   - Enforced password complexity via `Default Domain Policy`.  

## **Screenshots**  
![AD Users and Computers](screenshots/ad-users.png)  

## **Challenges & Fixes**  
- **Issue**: DNS resolution failed after promotion.  
- **Fix**: Manually set DNS to `127.0.0.1` in NIC settings. 

