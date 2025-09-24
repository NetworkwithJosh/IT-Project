# DNS

## What is DNS?

DNS (Domain Name System) is a protocol that translates human-readable domain names (E.g. google.com) into IP addresses (E.g. 142.250.190.78), allowing computers to locate and communicate with each other over the Internet or a private network.

---
## DNS Server

A DNS Server is a computer or network device that stores and manages domain name records and responds to DNS queries by resolving domain names into IP addresses.
![Screenshot](images/DNS1.jpg)

---
> **Tip:** Before installing DNS in the server, the server needs to have a static IP address.

- Navigate to the Server Manager → Local Server → on the page that's up → go to `Ethernet0` → click on it → `Ethernet0 Properties`
- Click on **Internet Protocol Version 4 (TCP/IPv4)** → Properties
  - → Use the following IP address (Static IP address)
- Disable **Internet Protocol Version 6 (TCP/IPv6)** and close
![Screenshot](images/DNS2.jpg)
![Screenshot](images/DNS3.jpg)

---

> If you go back to the Local Server, you will observe the static IP that was just create

# Installing DNS Server

1. Go to **Server Manager**  
2. On the top, click on **Manage** → **Add Roles & Features**  
3. Click **Next** before you begin  
4. **Role-based or feature-based installation** → **Next**  
5. **Server Selection** → **Next**  
6. **Server Roles** (click on **DNS Server**) → Add role and click **Next**  
7. Click **Next** and **Install**
![Screenshot](images/DNS4.jpg)
![Screenshot](images/DNS5.jpg)

---

## Navigating to DNS Zones

1. Navigate to **Tools** on the Server Manager and click on **DNS**  
2. Under **Server 2022**, expand →  
   - **Forward Lookup Zones**  
   - **Reverse Lookup Zones**
![Screenshot](images/DNS6.jpg)
---

## Forward Lookup Zones (FLZ)
- A **DNS Zone** that translates a **domain name** (e.g., `nykarson.com`) into an **IP address** (e.g., `172.168.1.10`)  
- It allows users to access websites and network resources using domain names instead of IP addresses
---
## Reverse Lookup Zones (RLZ)

- Performs the **opposite function** of FLZ  
- Translates an **IP address** (e.g., `172.168.1.10`) back into a **domain name** (e.g., `nykarson.com`)  
- It is used for **security**, **logging**, and **troubleshooting**
![Screenshot](images/DNS7.jpg)
# Creating a Zone

## Forward Lookup Zone

1. Right-click on **Forward Lookup Zones** → **New Zone** → **Next**
2. **Zone Type** → Select **Primary Zone**, uncheck **Store the zone in Active Directory** → **Next**
3. **Zone Name**: `njikason.com` → **Zone File** (leave as default) → **Next**
4. **Dynamic Update**: Select **Do not allow** → **Finish**
---
## Reverse Lookup Zone

1. Right-click on **Reverse Lookup Zones** → **New Zone** → **Next**
2. **Zone Wizard** → Select **Primary Zone** → **Next**
3. Skip **Active Directory Zone Replication** → **Next**
4. Choose **IPv4 Reverse Lookup Zone** → **Next**
5. **Network ID**: `10.1.10` → **Next**
6. Select **Do not allow dynamic updates** → **Next** → **Finish**
![Screenshot](images/DNS8.jpg)
---
# Creating a New Host (Forward Lookup Zone)
