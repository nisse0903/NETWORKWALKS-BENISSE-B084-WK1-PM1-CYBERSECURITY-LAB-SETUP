# NETWORKWALKS-BENISSE-B084-WK1-PM1-CYBERSECURITY-LAB-SETUP

## Author
- Benisse Villasoto
- My LinkedIn: [https://www.linkedin.com/in/benisse-villasoto-76194b381/](https://www.linkedin.com/in/benisse-villasoto-76194b381/)

## Project Information
- **Program Name:** Cybersecurity at Networkwalks | **Week:** 01 | **Project:** Cybersecurity and Pentesting Lab Setup | **Repository:** GitHub

## Project Overview

This project sets up a virtual cybersecurity and penetration-testing lab using VirtualBox and Kali Linux. The lab provides a safe, controlled space for practicing scanning, vulnerability testing, and other security-testing activities as often as needed. It runs on a private virtual network, so additional machines can be added later as targets for authorized testing.

## Lab Setup Procedure

### Step 1. Install 7-Zip & VirtualBox

![Install 7-Zip and VirtualBox](images/1-screenshot-VirtualBox.png)

### Step 2. Create the NAT Network

![Create NAT Network](images/2-screenshot-VB-networksettings.png)

### Step 3. Import Kali Linux

![Import Kali Linux](images/3-screenshot-Kali-Linux.png)

### Step 4. Configure the Kali Linux Network (Static IP)

![Static IP Configuration](images/4-screenshot-KL-networksettings.png)

### Step 5. Create a Clean VM Snapshot

![Clean VM Snapshot](images/5-screenshot-snapshot.png)

### Step 6. Functionality Verification

![Functionality Verification](images/6-screenshot-KL-testing.png)

## Lab Verification

| Test | Command | Screenshot |
|------|---------|------------|
| Check IP address | `ip a` | <img src="images/ip-a.png" width="400"> |
| Test gateway | `ping 10.0.0.1` | <img src="images/ping-1001.png" width="400"> |
| Test Internet connectivity | `ping 8.8.8.8` | <img src="images/ping-8888.png" width="400"> |
| Test DNS resolution | `nslookup networkwalks.com` | <img src="images/nslookup.png" width="400"> |
| Verify Nmap | `nmap --version` | <img src="images/nmap.png" width="400"> |
| Verify snapshot | Restore snapshot and run `ip a` | <img src="images/restored-snap.png" width="400"> |

## Problems Encountered and Solutions

**Internet Connectivity After Static IP Configuration:** I set up a static IP and tested it, and it worked. After I shut down the VM and opened it again, the connection was gone. To fix it, I ran `sudo dhclient eth0` in the terminal. This asked the DHCP server to give the `eth0` interface an IP address, and the connection worked again.

![dhclient Fix](images/problem-dhclient.png)

## 5. What I Learned

- **NAT vs NAT Network & VM Networking:** A NAT Network lets VMs on the same virtual network talk to each other and still reach the internet. This makes it better for a multi-machine lab.
- **Static IP Configuration:** I learned how to configure and verify IPv4 addressing, subnet masks, gateways, and DNS settings in Kali Linux.
- **Troubleshooting Network Connectivity:** I learned to use `sudo dhclient eth0` to request a new IP address when the connection drops.
- **VM Snapshots & Documentation:** I learned to take a clean snapshot before risky work so I can recover easily. I also learned that documenting commands, problems, and solutions is an important part of a cybersecurity project.

## Security and Ethical Use

This lab is intended strictly for educational purposes.

## Resources
- 7-Zip: https://7-zip.org/download.html
- VirtualBox: https://virtualbox.org/wiki/Downloads
- Kali Linux: https://kali.org/get-kali
