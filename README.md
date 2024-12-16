# TCPDUMP Analysis

## Objective
The TCPDUMP analysis project aimed to familiarize users with the installation and utilization of TCPDUMP, a powerful network packet analyzer. This lab focused on capturing and analyzing network traffic, applying filters, and saving captures for further examination. The hands-on experience provided insights into both offensive and defensive uses of packet analysis in cybersecurity.

### Skills Learned
- Proficient in installing and configuring TCPDUMP on various operating systems (Linux and Windows).
- Mastery of network traffic capture techniques and filtering methods.
- Ability to analyze packet data for troubleshooting and monitoring purposes.
- Enhanced understanding of network protocols and their vulnerabilities.
- Development of practical skills in using command-line tools for cybersecurity analysis.

### Tools Used
- **TCPDUMP**: A command-line packet analyzer for capturing network traffic.
- **Virtual Machines (VMs)**: Used for creating isolated environments (Kali Linux and Windows Server 2019).
- **Network Protocols**: Knowledge of TCP/IP, DNS, HTTPS, and others.

## Steps

### Step 1: TCPDUMP Installation on Alma

1. **Create an Alma Virtual Machine**:
   - Ensure that the network settings are attached to the NAT Network/LAB-NAT so that your VM can reach the internet.

2. **Run System Update**:
   - Execute the command: 
     ```bash
     yum update -y && yum upgrade -y
     ```

3. **Install TCPDUMP**:
   - Run the command: 
     ```bash
     yum install tcpdump -y
     ```

---

### Step 2: TCPDUMP Installation on Windows Server 2019/2022

1. **Create a Windows Server 2019/2022 Virtual Machine**:
   - Ensure NAT Network/LAB-NAT settings.

2. **Download TCPDUMP**:
   - Navigate to [TCPDUMP Download Page](https://www.microolap.com/products/network/tcpdump/download/) and download the .zip file.

3. **Extract Files**:
   - Right-click and copy the file to `C:\users\Administrator`.

4. **Run TCPDUMP**:
   - Open Command Prompt and navigate to the directory where TCPDUMP.exe is located.
   - Execute: 
     ```bash
     tcpdump
     ```

---

### Step 3: Basic TCPDUMP Usage

1. **Identify Interface**:
   - Switch to root user in Kali using:
     ```bash
     sudo su root
     ```
   - Identify active interface with:
     ```bash
     ifconfig
     ```

2. **Capture All Traffic**:
   - Use the following command to capture traffic:
     ```bash
     tcpdump -i eth0
     ```
   - Stop capture with `CTRL + C`.

---

### Step 4: Create a Folder Named "capture" in Your Home Directory

- Create a new directory called "capture":
  ```bash
  mkdir ~/capture

---

### Step 5: Advanced Filters

- To capture traffic for a specific host:
  ```bash
  tcpdump -i eth0 host 10.10.10.11

- To capture traffic for a specific protocol (e.g., HTTP):
  ```bash
  tcpdump -i eth0 tcp port 80
  ```

- To write captured traffic to a file in your new directory:
  ```bash
  tcpdump -i eth0 -w ~/capture/http-cap.pcap tcp port 80
  ```
---

## Conclusion

This lab provides essential skills in using TCPDUMP for network analysis, critical for various roles in cybersecurity.
