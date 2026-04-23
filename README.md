# Tenable Nessus Essentials Vulnerability Scanning Lab

![Platform](https://img.shields.io/badge/Platform-VirtualBox-blue)
![Scanner](https://img.shields.io/badge/Vulnerability%20Scanner-Nessus%20Essentials-0f172a)
![Host](https://img.shields.io/badge/Host-Ubuntu%2022.04-E95420)
![Target](https://img.shields.io/badge/Target-Kali%20Linux-268BEE)
![Focus](https://img.shields.io/badge/Focus-Vulnerability%20Assessment-darkgreen)
![Status](https://img.shields.io/badge/Project-Completed-success)

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Lab Environment](#lab-environment)
- [Tools Used](#tools-used)
- [Skills Demonstrated](#skills-demonstrated)
- [Project Walkthrough](#project-walkthrough)
  - [1. Download and Verify Nessus](#1-download-and-verify-nessus)
  - [2. Install and Start Nessus](#2-install-and-start-nessus)
  - [3. Complete Initial Setup in the Browser](#3-complete-initial-setup-in-the-browser)
  - [4. Identify the Target System](#4-identify-the-target-system)
  - [5. Configure and Launch the Scan](#5-configure-and-launch-the-scan)
  - [6. Review Findings and Export the Report](#6-review-findings-and-export-the-report)
- [Results](#results)
- [What Employers Should Notice](#what-employers-should-notice)
- [Screenshots](#screenshots)
- [Key Takeaways](#key-takeaways)

---

## Overview

This project demonstrates how to deploy and configure **Tenable Nessus Essentials** on **Ubuntu 22.04** inside a **VirtualBox lab**, then use it to perform a vulnerability assessment against a **Kali Linux** target.

The lab walks through the full process from installation and service validation to target discovery, scan configuration, vulnerability review, and report generation. This project highlights practical exposure to vulnerability management workflows in a controlled lab environment.

> **Note:** This project was conducted in an authorized home lab environment for educational and defensive security purposes.

---

## Objectives

- Install Nessus Essentials on Ubuntu
- Verify package integrity before installation
- Start and validate the Nessus service
- Access the Nessus web interface and complete setup
- Identify the target Kali Linux system on the lab network
- Configure and run a vulnerability scan
- Review findings and export a report
- Document the workflow in a professional, repeatable format

---

## Lab Environment

### Virtual Machines
- **Ubuntu 22.04** – Nessus host
- **Kali Linux** – scan target

### Virtualization
- **VirtualBox**

### Network Context
- Local lab subnet used for host discovery and vulnerability scanning

---

## Tools Used

- **Tenable Nessus Essentials**
- **sha256sum**
- **route**
- **ifconfig**
- **nmap**

---

## Skills Demonstrated

- Vulnerability scanner deployment and setup
- Linux package installation and service management
- File integrity validation
- Basic network enumeration
- Target discovery in a segmented lab
- Vulnerability assessment workflow
- Report generation and documentation
- Security lab troubleshooting and validation

---

## Project Walkthrough

## 1. Download and Verify Nessus

The first step was to download **Nessus Essentials** from Tenable and register for an activation code.

After downloading the package, the installer hash was checked to validate file integrity before installation.

### Command Used
```bash
sha256sum Downloads/Nessus-10.7.4-ubuntu1404_amd64.deb

```

This step demonstrates good security hygiene by verifying that the downloaded package matches the expected hash before installation.

---

## 2. Install and Start Nessus

After confirming the package integrity, Nessus was installed from the Ubuntu terminal.

### Commands Used

```bash
cd
ls
sudo dpkg -i Nessus-10.7.4-ubuntu1404_amd64.deb

```
  
<p align="center">
<img src="https://imgur.com/S4WH61N.png" height="80%" width="80%" alt="Project walk-through"/>

<h3>After it has installed it will look like this:</h3>
<p align="center">
<img src="https://imgur.com/NrFhBtS.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Open a new terminal in Ubuntu and run the commands to start Nessus and check the status to be sure it is (active)running:</h3>
  
 ## Usage:
    sudo systemctl start nessusd
    sudo systemctl status nessusd
<p align="center">
<img src="https://imgur.com/ovmNpvD.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Copy the link in the first terminal and paste it into your browser:</h3>
<p align="center">
<img src="https://imgur.com/uHw0K0O.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>You will get a 'Warning' notice, but just hit the 'Advanced' button and then hit the 'Accept the Risk and continue':</h3>
<p align="center">
<img src="https://imgur.com/yo33RlI.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Once the Welcome page comes up hit the button to continue:</h3>
<p align="center">
<img src="https://imgur.com/th8Fefp.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Select 'Register for Nessus Essentials' and hit continue:</h3>
<p align="center">
<img src="https://imgur.com/vitSLAJ.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Hit the skip button since we have already registered:</h3>
<p align="center">
<img src="https://imgur.com/YJWThm6.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Open the email sent from Tenable Nessus and copy the activation code:</h3>
<p align="center">
<img src="https://imgur.com/aDPmWpX.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Enter the activation code here and hit continue:</h3>
<p align="center">
<img src="https://imgur.com/1lYjnTa.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Create a username and password then hit submit:</h3>
<p align="center">
<img src="https://imgur.com/jtGP7ga.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Wait for initializing and downloading of plugins:</h3>
<p align="center">
<img src="https://imgur.com/9v0QvSM.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Again, wait for more initializing:</h3>
<p align="center">
<img src="https://imgur.com/r9pd14K.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>You will be notified when it is complete:</h3>
<p align="center">
<img src="https://imgur.com/iVymTOE.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Open a terminal in Ubuntu and run the commands to understand what the default gateway and Ubuntu IP addresses are:</h3>
  
 ## Usage:
    route
    ifconfig
<p align="center">
<img src="https://imgur.com/R5kMq4M.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>In the same terminal run the command to understand what the IP address of the Kali machine is:</h3>
  
 ## Usage:
    sudo nmap -PR -sn 10.0.2.0/24
<p align="center">
<img src="https://imgur.com/Y03XZPR.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>We are now ready to initialize a new scan:</h3>
<p align="center">
<img src="https://imgur.com/SYVI2N8.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>To scan Kali, we will be choosing the Basic Scan:</h3>
<p align="center">
<img src="https://imgur.com/Jw775Y3.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Enter the name, description, and targets into the appropriate fields:</h3>
<p align="center">
<img src="https://imgur.com/UYFGgH1.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>In the discovery tab, choose the type of port scan you would like. In this project we will be scanning all ports:</h3>
<p align="center">
<img src="https://imgur.com/HA26EEk.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>After you have completed choosing the settings hit the save button:</h3>
<p align="center">
<img src="https://imgur.com/VZVFOqi.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>In the folowing screen, click the Launch button to start the scan:</h3>
<p align="center">
<img src="https://imgur.com/UrCOXRS.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>The scan will be complete when the check mark appears. Click anywhere in the rectangle to view the results:</h3>
<p align="center">
<img src="https://imgur.com/82fxdOy.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Here we see a list of tabs with one showing the vulnerabilities:</h3>
<p align="center">
<img src="https://imgur.com/Lk1Pgzo.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Click the vulnerabilitites tab for a detailed view, then click the individual vulnerabilities for more information:</h3>
<p align="center">
<img src="https://imgur.com/CyYOyMX.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Here is a description and a solution to fix the problem:</h3>
<p align="center">
<img src="https://imgur.com/o6ffQNJ.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Go back to the main vulnerabilities page to download a report:</h3>
<p align="center">
<img src="https://imgur.com/5bCU94K.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Select the type of report you want to generate and click Generate Report:</h3>
<p align="center">
<img src="https://imgur.com/x5mwp7D.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>The report will be found in the downloads folder:</h3>
<p align="center">
<img src="https://imgur.com/e6zlq8o.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Open the file to view the report generated by Nessus:</h3>
<p align="center">
<img src="https://imgur.com/AXBDlRw.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
  

  
</p>


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
