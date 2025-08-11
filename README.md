# Active Directory Setup on Windows Server 2022 
**Goal**: Deploy a functional AD Domain Controller with users, OUs, and Group Policies.

##  **Steps**
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
     
3. **ADDS Install Windows Server 2022** 
   - Installed ADDS Active Directory Domain Services Role
   - Promote the Server to a DC Domain Controller
   - Domain name will be: Slaptop.com
   - Check DNS with the nslookup tool in PowerShell
   - Reboot the server to test new configurations
   - Created Reverse Lookup Zone for Server
  
4. **



## **Screenshots**  
![AD Users and Computers](screenshots/ad-users.png)  

## **Challenges & Fixes**  
- **Issue**: DNS resolution failed after restart.
- **Fix**: Disabled DHCP and IPv6. Manually set IPv4 address in NIC settings.
  
- **Issue**: DNS resolution failed after restart
- **Fix**: Manually set DNS in NIC settings.

