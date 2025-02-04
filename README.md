# Azure Networking Components

## 1️⃣ Virtual Network (VNet)
### 🔹 What it is:
A **Virtual Network (VNet)** is a logically isolated network in Azure, similar to a traditional on-premises network.

### 🔹 Key Features:
✅ Allows **communication between Azure resources** (VMs, databases, etc.)  
✅ Can **connect to on-premises networks** using VPN or ExpressRoute  
✅ Supports **subnets** for better network segmentation  
✅ **Enables private and secure communication**  

### 🔹 Use Case:
- Deploy a **private network** for your Azure resources  
- Connect on-premises data centers to **Azure resources**  

---

## 2️⃣ Subnet
### 🔹 What it is:
A **subnet** is a smaller segment within a VNet that helps organize and manage network traffic.

### 🔹 Key Features:
✅ **Isolate workloads** for better security and management  
✅ Apply **Network Security Groups (NSG)** for traffic control  
✅ Each subnet has its own **IP address range**  

### 🔹 Use Case:
- Create separate subnets for **databases, web apps, and app servers**  

---

## 3️⃣ Network Security Group (NSG)
### 🔹 What it is:
NSG is a firewall-like security rule set that **controls inbound and outbound traffic** at the subnet or VM level.

### 🔹 Key Features:
✅ Allow or deny **specific IPs, ports, and protocols**  
✅ Applied at **subnet or NIC level**  
✅ Helps secure **VMs and resources**  

### 🔹 Use Case:
- Block all **unwanted traffic** and allow only specific **ports like 22 (SSH) or 3389 (RDP)**  
- Allow **only internal VMs to communicate with the database**  

---

## 4️⃣ Application Security Group (ASG)
### 🔹 What it is:
An **Application Security Group (ASG)** simplifies security management by grouping VMs logically.

### 🔹 Key Features:
✅ Instead of defining IP-based NSG rules, group **VMs into ASGs**  
✅ Useful for **dynamic workloads**  
✅ Improves security management  

### 🔹 Use Case:
- Create an ASG for **Web VMs** and allow only HTTP/HTTPS traffic  
- Group **Database VMs** in another ASG and allow only **MySQL or PostgreSQL traffic**  

---

## 5️⃣ Public IP & Private IP
### 🔹 What it is:
Azure resources can have **public and private IPs** to control access.

### 🔹 Key Features:
✅ **Public IP** → Accessible over the Internet  
✅ **Private IP** → Accessible only within the VNet  
✅ Supports **Static & Dynamic IP assignment**  

### 🔹 Use Case:
- Assign a **public IP** to a VM for Internet access  
- Assign a **private IP** to an internal database server  

---

## 6️⃣ Azure Load Balancer (ALB)
### 🔹 What it is:
A **Layer 4 (TCP/UDP) load balancer** that distributes traffic to backend VMs.

### 🔹 Key Features:
✅ Supports **public and internal load balancing**  
✅ Provides **automatic failover**  
✅ Uses **health probes** to check VM availability  

### 🔹 Use Case:
- Distribute **web traffic** across multiple VMs  
- Load balance **database connections**  

---

## 7️⃣ Azure Application Gateway (AAG)
### 🔹 What it is:
A **Layer 7 (HTTP/HTTPS) load balancer** with **Web Application Firewall (WAF)**.

### 🔹 Key Features:
✅ **URL-based routing** (e.g., `/api` → Backend A, `/dashboard` → Backend B)  
✅ **SSL/TLS termination** for security  
✅ Protects against **DDoS and cyber threats**  

### 🔹 Use Case:
- Securely route **API requests to different backend pools**  
- Enable **WAF to protect against SQL injection & XSS attacks**  

---

## 8️⃣ Azure DNS
### 🔹 What it is:
Azure DNS is a **domain name system (DNS) service** for managing domain resolution.

### 🔹 Key Features:
✅ Provides **fast and secure domain name resolution**  
✅ Supports **custom domain mapping**  
✅ Integrated with **Azure Private DNS**  

### 🔹 Use Case:
- Map **www.example.com** to an **Azure Web App**  
- Manage **private DNS records** within a VNet  

---

## 9️⃣ Azure ExpressRoute
### 🔹 What it is:
ExpressRoute is a **dedicated private connection** between on-premises and Azure.

### 🔹 Key Features:
✅ **High-speed, low-latency private connection**  
✅ Bypasses the **public Internet**  
✅ **More secure than VPN**  

### 🔹 Use Case:
- Connect **on-premises data centers to Azure** securely  
- Ensure **high-speed connectivity** for business applications  

---

## 🔟 Azure Virtual Private Network (VPN)
### 🔹 What it is:
Azure VPN allows **secure connectivity** between Azure and on-premises.

### 🔹 Key Features:
✅ Supports **Point-to-Site (P2S) & Site-to-Site (S2S) VPNs**  
✅ Uses **IPsec/IKE for security**  
✅ Works over **public Internet**  

### 🔹 Use Case:
- Connect **remote employees securely to Azure**  
- Establish a **secure tunnel between an on-premises network and Azure**  

---

## 1️⃣1️⃣ Azure Firewall
### 🔹 What it is:
Azure Firewall is a **cloud-native network security service**.

### 🔹 Key Features:
✅ **Filter inbound and outbound traffic**  
✅ Supports **DDoS protection**  
✅ Enforces **application rules (FQDN filtering)**  

### 🔹 Use Case:
- Secure Azure workloads with **stateful firewall rules**  
- Block or allow **specific URLs or IPs**  

---

## 1️⃣2️⃣ Azure Front Door
### 🔹 What it is:
A **global application load balancer and CDN** that optimizes traffic routing.

### 🔹 Key Features:
✅ **Global load balancing** for apps across multiple regions  
✅ **DDoS protection & Web Application Firewall (WAF)**  
✅ **Fast content delivery using caching**  

### 🔹 Use Case:
- Improve **performance for global users** accessing a website  
- Enable **failover** between multiple Azure regions

- ## Azure Networking Components

### 1. Network Security Group (NSG)
NSG acts as a firewall that controls inbound and outbound traffic to Azure resources (such as virtual machines, subnets, and NICs).

#### Key Features of NSG:
✅ **Rule-based filtering** – NSG contains security rules that allow or deny traffic based on:
- Source & Destination IPs
- Port Numbers (e.g., HTTP - 80, RDP - 3389)
- Protocol (TCP/UDP)

✅ **Can be applied to:**
- Subnets (affects all resources in that subnet)
- NICs (applies to specific VMs or instances)

✅ **Default Security Rules:** Azure NSG comes with some predefined rules, such as:
- Allow Virtual Network traffic
- Allow Azure Load Balancer traffic
- Deny all inbound traffic by default

#### Example Use Case:
- You want to allow SSH (port 22) access only from your office IP and deny all other inbound SSH connections.
- You want to restrict RDP (port 3389) access to only certain users.

### 2. Application Security Group (ASG)
ASG is a logical grouping of Virtual Machines (VMs) within a Virtual Network for easier management of NSG rules. Instead of applying NSG rules using individual IP addresses, you can apply them to ASGs, which simplifies rule management.

#### Key Features of ASG:
✅ **Allows grouping of VMs logically** – Even if VMs are in different subnets, they can be grouped under the same ASG.
✅ **Dynamic association** – If a new VM is added to the ASG, it automatically inherits the existing security rules.
✅ **Simplifies NSG rules** – Instead of managing individual IP addresses, you manage security rules based on ASG names.

#### Example Use Case:
- You have multiple web servers (VMs) that should allow only HTTP (80) and HTTPS (443) traffic. Instead of creating rules for each VM, you can create an ASG (e.g., WebServers) and define the rule in NSG once for that ASG.
- Your backend servers should only communicate with frontend servers, not with other VMs. You can create ASGs for both layers and apply security rules accordingly.

### 3. Key Differences Between NSG & ASG

| Feature | NSG (Network Security Group) | ASG (Application Security Group) |
|---------|----------------------------|---------------------------------|
| Purpose | Controls inbound/outbound traffic | Groups VMs for applying NSG rules |
| Scope | Applied to subnets or NICs | Assigned to VMs within the same VNet |
| Use Case | Block/Allow traffic based on IP, port, protocol | Apply rules based on logical groups of VMs |
| Example | Allow SSH only from a specific IP | Allow WebServers ASG to communicate with Database ASG |

### Conclusion:
- Use **NSG** when you need to control traffic flow at the subnet or NIC level.
- Use **ASG** when you want to logically group VMs and apply security rules more efficiently.
- **NSG and ASG can work together** – you define NSG rules using ASGs instead of individual IPs, making security management more scalable and dynamic.

# User Data and Custom Data in Azure

In Azure, **User Data** and **Custom Data** are used to pass information or scripts to virtual machines (VMs) during provisioning.

## 1. User Data

**User Data** is a script or command that is executed when the VM boots for the first time. It is mainly used for:

- Automating VM configuration during startup
- Installing software (e.g., Apache, MySQL)
- Running initialization tasks

### Key Features of User Data:
- ✅ Executed only once during the first boot
- ✅ Can contain shell scripts (Linux) or PowerShell scripts (Windows)
- ✅ Used for automatic configuration
- ✅ Stored in Azure Metadata Service

### Example of User Data:

#### For Linux VM (Bash Script)
```bash
#!/bin/bash
sudo apt update -y
sudo apt install apache2 -y
systemctl start apache2
systemctl enable apache2

# Custom Data in Azure

**Custom Data** is a feature in Azure that allows you to pass information or scripts to a virtual machine (VM) during provisioning. Unlike **User Data**, Custom Data is not automatically executed. Instead, it is provided to the VM as plain text or a script, which can be accessed and used later by the user.

---

## Key Features of Custom Data:
- ✅ Passed as plain text or script during VM creation
- ✅ Not executed automatically
- ✅ Can be retrieved manually from inside the VM
- ✅ Useful for storing configuration details (e.g., API keys, environment variables, configuration files)

---

## Use Cases for Custom Data:
- Storing metadata or configuration files for later use
- Passing environment-specific variables (e.g., API keys, database connection strings)
- Providing setup instructions or scripts that need to be executed manually
- Sharing data between VMs or with external systems

---

## How to Retrieve Custom Data

### For Linux VMs:
Custom Data can be accessed from the following location:
```bash
sudo cat /var/lib/cloud/instances/$(hostname)/user-data.txt
---
