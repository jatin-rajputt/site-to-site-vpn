# 🛡️ Site-to-Site VPN Project (GNS3 + VirtualBox)

This project demonstrates a secure **Site-to-Site VPN** setup between two remote offices using **IPSec VPN** in **GNS3**, with an internal **PPTP VPN** between Windows VMs. The simulation provides a practical view of encrypted inter-office communication and VPN tunneling.

---

## 🖥️ Network Topology

![Network Topology](https://github.com/jatin-rajputt/site-to-site-vpn/blob/main/topology.png)

---

## 📌 Project Overview

| Component     | Details                            |
|---------------|-------------------------------------|
| VPN Type      | IPSec Site-to-Site (R2 ↔ R3)        |
| Internal VPN  | PPTP VPN (Win1 ↔ Win2)              |
| Routing       | Static routes used on routers       |
| Simulation    | Built in GNS3 + VirtualBox          |

---

## 🧰 Tools & Technologies Used

- [GNS3](https://www.gns3.com/)
- [VirtualBox](https://www.virtualbox.org/)
- Cisco Routers (IOS image: `c3725`)
- Windows Server and Windows Client (VirtualBox VMs)
- VPCS for endpoint testing
- VPN Protocols: IPSec & PPTP

---

## 🗂️ Network Segments

| Office A                 | Office B                 |
|--------------------------|--------------------------|
| Network: 192.168.5.0/24  | Network: 192.168.6.0/24  |
| Devices: PC1, Win1       | Devices: Win2, PC2       |
| Router: R2               | Router: R3               |
| VPN to: R3 (via R1)      | VPN to: R2 (via R1)      |

---

## 🔐 Security Demonstration

- **IPSec VPN** ensures encrypted traffic through the public ISP (via Router R1).
- **PPTP VPN** provides internal encryption between Windows VMs across offices.
- A simulated **attacker (Kali Linux)** fails to intercept or break into the tunnel due to secure VPN setup.

---

## 📦 Download Virtual Machines

Download the Windows VMs (exported as `.ova` files) from the links below:

- 🖥️ **Windows Server VM (win-server.ova)**  
  [Download from Google Drive](https://drive.google.com/file/d/1scphRw3jhOG8Hz0JDiGi6zV0Jk_Go3RK/view?usp=drive_link)

- 🖥️ **Windows Client VM (win-client.ova)**  
  [Download from Google Drive](https://drive.google.com/file/d/1JhZDhkhOj01j-EgPpTcMPj6zKIK_6tf1/view?usp=drive_link)

> ⚠️ These files are large (~4 GB each). Make sure to extract or import them before running the project.

---

## 💻 How to Import OVA Files (VirtualBox)

1. Open **VirtualBox**
2. Go to `File` → `Import Appliance`
3. Browse and select the downloaded `.ova` file
4. Click **Next**, then **Finish**
5. Repeat for both Win1 and Win2 VMs

---

## 🧪 How to Run This Project

1. **Clone this repository**:
   ```bash
   git clone https://github.com/jatin-rajputt/site-to-site-vpn.git
   cd site-to-site-vpn
