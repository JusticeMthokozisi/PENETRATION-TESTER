# Metasploitable 2 Penetration Testing Lab

A comprehensive guide and walkthrough for identifying and exploiting vulnerabilities in the Metasploitable 2 vulnerable Linux machine.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=for-the-badge&logo=linkedin)](https://linkedin.oia.bio/0dvt1) 
[![Instagram](https://img.shields.io/badge/Instagram-Follow-pink?style=for-the-badge&logo=instagram)](https://insta.openinapp.co/3wrfc)

---

## 📖 Table of Contents
* [What is Metasploitable 2](#what-is-metasploitable-2)
* [System Requirements](#system-requirements)
* [Installation](#installation-of-metasploitable-2)
* [Network Scanning](#network-scan)
* [Exploitation Guides](#exploitation-guides)
    * [Port 21: FTP (Hydra & vsftpd 2.3.4)](#exploiting-port-21-ftp)
    * [Port 22: SSH (Brute Force & RSA)](#exploiting-port-22-ssh)
    * [Port 23: Telnet](#exploiting-port-23-telnet-credential-capture)
    * [Port 25: SMTP User Enumeration](#port-25-smtp-user-enumeration)
    * [Port 80: PHP_CGI Argument Injection](#exploiting-port-80-php_cgi)
    * [Port 139/445: Samba](#exploiting-port-139--445-samba)
    * [Port 5432: PostgreSQL](#exploiting-port-5432-postgresql)
    * [Port 6667: UnrealIRCd Backdoor](#exploiting-unrealircd-backdoorport-6667)
    * [Port 8080: Java RMI](#exploiting-port-8080-java-rmi)

---

## 🛡️ What is Metasploitable 2
Metasploitable 2 is an intentionally vulnerable Linux virtual machine designed for learning and practicing penetration testing. It contains many known security vulnerabilities that allow security students and professionals to practice identifying and exploiting security weaknesses in a safe lab environment.

> **Note:** Developed by Rapid7, it is commonly used with the Metasploit Framework to demonstrate real-world security attacks and defenses.

---

## 💻 System Requirements
To run Metasploitable 2, you need virtualization software and basic hardware resources.

### Hardware
* **Processor:** Dual-Core CPU or higher
* **RAM:** Minimum 2 GB (4 GB recommended)
* **Storage:** 10 GB free disk space

### Software
* VirtualBox or VMware Workstation
* **Kali Linux** (Used as the attacker machine)

---

## ⚙️ Installation of Metasploitable 2
1. **Download:** Get the VM from the official Rapid7 website.
2. **Extract:** Unzip the folder to find the `.vmdk` file.
3. **Setup:** Create a new VM in VirtualBox/VMware.
4. **Disk:** Attach the extracted `.vmdk` as the virtual hard disk.
5. **Login:** Default credentials are: 
   * **User:** `msfadmin`
   * **Pass:** `msfadmin`

⚠️ **WARNING:** Only run this in a controlled host-only lab environment. **Do not connect it to the internet.**

---

## 🔍 Network Scan
Scanning is the first step to discover active hosts and open ports.

**Command:**
```bash
nmap -sV -p- 192.168.179.138
