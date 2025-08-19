# Set-up-DHCP-Server
# Networking Lab – Router, Switches, and DHCP Setup

## Objective
Set up a basic network with:
- 1 Router
- 2 Switches
- 3 End devices per router
- DHCP configuration for automatic IP assignment

---

## Step-by-Step Instructions

1. **Start with the topology:**  
   - 1 router  
   - 2 switches  
   - 3 end devices for each router  

2. **Connect the devices:**  
   - PCs → Switches  
   - Switches → Router  

3. **Assign IP addresses** for each side.  

4. **Access the router CLI**  
   - Use the command:  
     ```bash
     enable
     config t
     ```

5. **Set the hostname:**  
   ```bash
   hostname R1

6. **Configure interfaces and assign IPs**
  int f0/0
  ip add 192.168.1.1 255.255.255.0
  no shut
  int f0/1
  ip add 192.168.2.1 255.255.255.0
  no shut
  exit

7. **Configure DHCP Pool A**
  ip dhcp pool A
  network 192.168.1.0 255.255.255.0
  default-router 192.168.1.1
  dns-server 8.8.8.8
  exit

8.**Exclude addresses from DHCP**
  ip dhcp excluded-address 192.168.1.1

9.**Configure DHCP for Pool B**
ip dhcp pool B
network 192.168.2.0 255.255.255.0
default-router 192.168.2.1
dns-server 8.8.8.8
exit

10.**Verify Connections**
On PCs, check DHCP settings.

Use ping to test communication across devices.
