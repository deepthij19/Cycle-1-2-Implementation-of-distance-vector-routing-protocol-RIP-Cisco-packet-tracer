# Cycle-1-2-Implementation-of-distance-vector-routing-protocol-RIP-Cisco-packet-tracer
# 🧪 EXPT.NO: 2  
📅 DATE: *(Insert Date)*

## 📌 TITLE  
**Implementation of Distance Vector Routing Protocol (RIP)**

---

## 🎯 AIM  
To connect computers in multiple networks using Distance Vector Routing Protocol and to verify the connectivity between computers.

---

## 🛠️ EQUIPMENTS REQUIRED

| S.No | Name                   | Quantity |
|------|------------------------|----------|
| 1    | Desktop Computer       | 4        |
| 2    | Cisco 1800 Router      | 2        |
| 3    | USB to Serial Converter| 2        |
| 4    | Cisco 2900 Switch      | 2        |
| 5    | CAT 6 Patch Cable      | 10       |
| 6    | Console Cable          | 2        |

---

## 🌐 IP ASSIGNMENT

| Name       | IP Address     | Subnet Mask     | Network      | Class | Gateway        |
|------------|----------------|-----------------|--------------|-------|----------------|
| PC0        | 192.168.0.1    | 255.255.255.0   | 192.168.0.0  | C     | 192.168.0.200  |
| PC1        | 192.168.0.2    | 255.255.255.0   | 192.168.0.0  | C     | 192.168.0.200  |
| PC2        | 192.168.1.1    | 255.255.255.0   | 192.168.1.0  | C     | 192.168.1.200  |
| PC3        | 192.168.1.2    | 255.255.255.0   | 192.168.1.0  | C     | 192.168.1.200  |
| PC4        | 192.168.2.1    | 255.255.255.0   | 192.168.2.0  | C     | 192.168.2.200  |
| PC5        | 192.168.2.2    | 255.255.255.0   | 192.168.2.0  | C     | 192.168.2.200  |
| Router0 F0/0 | 192.168.0.200 | 255.255.255.0   | 192.168.0.0  | C     | —              |
| Router0 S2/0| 192.168.1.200 | 255.255.255.0   | 192.168.1.0  | C     | —              |
| Router1 F0/0| 192.168.1.201 | 255.255.255.0   | 192.168.1.0  | C     | —              |
| Router1 S2/0| 192.168.2.200 | 255.255.255.0   | 192.168.2.0  | C     | —              |

---

## 🗺️ NETWORK DIAGRAM  
*(Insert diagram or screenshot from Packet Tracer)*

---

<img width="1542" height="812" alt="Screenshot 2026-10-16 101424" src="https://github.com/user-attachments/assets/65641066-561f-4c52-9630-8b7fe2382711" />

## 🧭 PROCEDURE

1. Open Cisco Packet Tracer software.  
2. Drag two 2900 switches, two Cisco 1800 routers, and four PC terminals into the workspace.  
3. Connect all devices using CAT 6 patch cables as per the network diagram.  
4. Configure IP addresses and gateways for all PCs.  
5. Configure and restart Router0.  
6. Configure and restart Router1.  
7. Verify connectivity between PCs using the `ping` command.

### Additional IP Configuration for PCs

| PC   | IP Address     | Subnet Mask     | Gateway        |
|------|----------------|-----------------|----------------|
| PC0  | 192.168.1.2    | 255.255.255.0   | 192.168.1.1    |
| PC1  | 192.168.1.3    | 255.255.255.0   | 192.168.1.1    |
| PC2  | 192.168.2.2    | 255.255.255.0   | 192.168.2.1    |
| PC3  | 192.168.3.2    | 255.255.255.0   | 192.168.3.1    |
| PC4  | 192.168.4.2    | 255.255.255.0   | 192.168.4.1    |
| PC5  | 192.168.4.3    | 255.255.255.0   | 192.168.4.1    |

---

## 💻 PROGRAM

### 🔧 Router0 Configuration

```bash
Router> enable
Router# configure terminal
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0
Router(config-router)# exit
```
### 🔧 Router1 Configuration
```bash
Router> enable
Router# configure terminal
Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.3.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.4.1 255.255.255.0
Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# router rip
Router(config-router)# version 2
Router(config-router)# network 192.168.3.0
Router(config-router)# network 192.168.4.0
Router(config-router)# exit
```


## ✅ OUTPUT VERIFICATION

## Router# show ip route

## Expected output on Router0:


<img width="1412" height="712" alt="Screenshot 2026-10-16 101543" src="https://github.com/user-attachments/assets/c4afec90-2ac1-4bf1-ac20-8b143a1cd2a0" />

## Expected output on Router1:


<img width="1402" height="711" alt="image" src="https://github.com/user-attachments/assets/e9707f32-9eb1-4181-b7a6-b11441362caf" />

## 📶  Ping Test Between PCs
## Example: Ping from PC0 to PC5


<img width="1531" height="767" alt="image" src="https://github.com/user-attachments/assets/7b20ead0-aba5-428c-9723-762dcc024c9c" />

## 📝  RESULT:

Thus, the computers in multiple networks using Distance Vector Routing Protocol are successfully connected and the connectivity between them is verified.
