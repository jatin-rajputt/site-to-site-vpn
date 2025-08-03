# 🛡️ Site-to-Site VPN Project (GNS3)

This project demonstrates a secure **Site-to-Site VPN** implementation between two remote offices using **IPSec VPN** in GNS3. Additionally, a **PPTP VPN** connection is configured between internal Windows machines, with an optional attacker (Kali Linux) placed in the ISP segment to simulate failed attacks due to encryption.

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
| Security Test | Kali attacker connected to R1 fails due to encryption |
| Simulation    | Built in GNS3 + VirtualBox          |

---

## 🧰 Tools & Technologies Used

- [GNS3](https://www.gns3.com/)
- [VirtualBox](https://www.virtualbox.org/)
- Windows Server & Windows Client
- Kali Linux
- Cisco Routers (R1, R2, R3)
- VPCS for test endpoints
- PPTP & IPSec Protocols

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

- **IPSec VPN** ensures that only encrypted traffic passes through the public network (ISP via R1).
- **Kali Attacker** connected to R1 attempts packet sniffing and MITM attacks using Wireshark, Ettercap, etc.
- Results:
  - Traffic between Win1 and Win2 remains encrypted and unreadable.
  - Attacker cannot view credentials or interfere with communication.

---

## 🧪 How to Run This Project

1. **Clone this repository**:
   ```bash
   git clone https://github.com/jatin-rajputt/site-to-site-vpn.git
