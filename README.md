# 🔐 Cybersecurity Lab Environment Setup

> **NetworkWalks Cybersecurity Internship | Batch B083 | Week 1 | Project 1**

## 📌 Project Overview

This project focuses on setting up a virtual cybersecurity testing laboratory using **Oracle VirtualBox** and **Kali Linux**.

The purpose of the lab is to create a controlled environment for cybersecurity learning and authorized security testing activities.

The lab uses a dedicated **NAT Network** with the `10.0.0.0/24` subnet, with Kali Linux configured as the attacking/security testing machine.

---

## 🎯 Objectives

- Install and configure Oracle VirtualBox
- Install/import Kali Linux as a virtual machine
- Create a NAT Network for the cybersecurity lab
- Configure network connectivity for Kali Linux
- Configure the required Kali Linux IP address
- Verify network connectivity and DNS resolution
- Enable VirtualBox clipboard and drag-and-drop
- Configure the `/downloads` shared folder
- Create a clean VM snapshot
- Prepare the environment for future cybersecurity projects

---

## 🏗️ Lab Architecture
<img width="1046" height="595" alt="Lab_Architecture" src="https://github.com/user-attachments/assets/fd4be516-dfa9-4090-b6ac-7ad3708c493b" />

---

## 🛠️ Tools & Technologies

| Tool / Technology | Purpose |
|---|---|
| Oracle VirtualBox | Virtualization platform |
| Kali Linux | Security testing machine |
| 7-Zip | Archive extraction |
| NAT Network | Virtual lab networking |
| Linux NetworkManager | Network configuration |

---

# 🚀 Lab Setup Procedure

## Step 1: Install 7-Zip

7-Zip was installed to extract the virtual machine package required during the lab setup.

### Evidence

<img width="420" height="268" alt="01-7zip-installed" src="https://github.com/user-attachments/assets/b3742f4b-35ac-4faf-aaca-6c8990929219" />


---

## Step 2: Install Oracle VirtualBox

Oracle VirtualBox was installed as the virtualization platform for creating and managing the cybersecurity laboratory.

### Evidence

<img width="646" height="507" alt="02-virtualbox-installed" src="https://github.com/user-attachments/assets/8e89ff55-5849-477c-994b-e7d8e4e92735" />


---

## Step 3: Configure the NAT Network

A custom NAT Network was configured in VirtualBox.

### Configuration

```text
Network: 10.0.0.0/24
Network Type: NAT Network
```

### Evidence

<img width="1920" height="1080" alt="03-nat-network" src="https://github.com/user-attachments/assets/86b3bb85-e3d4-4279-ae2d-11118f2ea6ec" />


---

## Step 4: Import Kali Linux

Kali Linux was downloaded and imported into Oracle VirtualBox as the security testing/attacking machine.

### Evidence

<img width="1917" height="1078" alt="04-kali-linux" src="https://github.com/user-attachments/assets/123d3079-0c2c-43a3-86de-3165db4020b4" />


---

## Step 5: Configure Kali Linux Network

The Kali Linux virtual machine was connected to the configured NAT Network.

### Network Configuration

```text
Network Type: NAT Network
Network Name: NatNetwork
```

### Evidence

<img width="993" height="648" alt="05-kali-network-settings" src="https://github.com/user-attachments/assets/107ddbd1-5084-44ae-bd32-6df019d8ae80" />


---

## Step 6: Configure Kali Linux IP Address

The Kali Linux VM was configured with the required IPv4 address.

```text
IP Address: 10.0.0.2/24
Gateway: 10.0.0.1
DNS: 8.8.8.8
```

### Evidence

<img width="1920" height="983" alt="06-kali-ip-configuration" src="https://github.com/user-attachments/assets/4ea73af6-e501-48d0-b8a3-80ff03f7d856" />


---

## Step 7: Verify Network Connectivity

Network connectivity was verified from Kali Linux.

### Check IP Address

```bash
ip a
```

### Test Gateway

```bash
ping 10.0.0.1
```

### Test Internet Connectivity

```bash
ping 8.8.8.8
```

### Test DNS Resolution

```bash
nslookup networkwalks.com
```

The tests were used to verify the Kali IP configuration, gateway connectivity, Internet access, and DNS resolution.

### Evidence

<img width="1920" height="982" alt="07-internet-connectivity" src="https://github.com/user-attachments/assets/f15cb5d5-ea7a-453d-9352-c26593239b96" />


---

## Step 8: Create VM Snapshot

A clean snapshot of the configured Kali Linux VM was created.

The snapshot provides a baseline recovery point before performing future cybersecurity exercises.

### Evidence

<img width="1917" height="1078" alt="08-kali-snapshot" src="https://github.com/user-attachments/assets/5d44fddb-a1d6-45ee-88df-6d219c0add70" />


---

# 🔎 Lab Verification

| Test | Command / Verification | Expected Result |
|---|---|---|
| IP Address | `ip a` | Kali IP displayed |
| Gateway | `ping 10.0.0.1` | Successful replies |
| Internet | `ping 8.8.8.8` | Successful replies |
| DNS | `nslookup networkwalks.com` | Domain resolves |
| Nmap | `nmap --version` | Nmap version displayed |
| Snapshot | Restore snapshot + `ip a` | Baseline restored |

---

# 🛠️ Troubleshooting

## Internet Connectivity Issue

If Kali Linux does not have Internet connectivity after configuring the static IP, the following checks can be performed:

1. Verify that the NAT Network was created correctly.
2. Check the VirtualBox network adapter configuration.
3. Check that another VM is not using `10.0.0.2`.
4. Restart the Kali network connection.
5. Restart the virtual machine if required.

For the NetworkWalks lab environment, the following NetworkManager commands can be used when the documented connectivity issue occurs:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"
```

> **Note:** The actual NetworkManager connection name can differ between systems. Verify the connection name before running the commands.

---

# 📚 What I Learned

Through this project, I gained practical experience with:

- Virtualization using Oracle VirtualBox
- Kali Linux virtual machine setup
- NAT Network configuration
- IPv4 addressing and subnetting
- Gateway and DNS configuration
- Basic network connectivity verification
- VirtualBox shared folders
- Clipboard and drag-and-drop integration
- VM snapshots and recovery points
- Building a controlled environment for cybersecurity practice

---

# 🔐 Security & Ethical Use

This laboratory is intended for **education, cybersecurity practice, and authorized security testing**.

All testing activities should be performed only on systems that I own or on systems for which I have explicit permission to test.

---

# 📸 Project Evidence

Screenshots included in this repository document the configuration and verification steps completed during the lab setup.

---

# 🎓 Internship Information

| Field | Details |
|---|---|
| Organization | NetworkWalks |
| Batch | B083 |
| Week | 1 |
| Project | WK1-PM1 |
| Project Name | Cybersecurity Lab Setup |

---

# 🔗 Resources

- [7-Zip](https://7-zip.org/)
- [Oracle VirtualBox](https://www.virtualbox.org/)
- [Kali Linux](https://www.kali.org/)
