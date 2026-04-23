# Nessus Essentials Vulnerability Assessment Lab

![Nessus](https://img.shields.io/badge/Vulnerability%20Scanner-Nessus-00C176)
![Ubuntu](https://img.shields.io/badge/Platform-Ubuntu-E95420)
![Kali Linux](https://img.shields.io/badge/Target-Kali%20Linux-268BEE)
![Nmap](https://img.shields.io/badge/Recon-Nmap-00457C)
![Project Type](https://img.shields.io/badge/Project-Homelab-blueviolet)

## Overview

This project documents a hands-on vulnerability assessment lab using **Nessus Essentials** to scan a **Kali Linux** system from an **Ubuntu** machine in a virtualized environment. The walkthrough covers installation, initial configuration, service startup, basic network discovery, scan creation, vulnerability review, and report generation.

This lab demonstrates foundational vulnerability management skills that are directly relevant to security operations, defensive validation, and entry-level security analyst work.

---

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Lab Environment](#lab-environment)
- [Tools Used](#tools-used)
- [Skills Demonstrated](#skills-demonstrated)
- [Assessment Workflow](#assessment-workflow)
- [Step-by-Step Walkthrough](#step-by-step-walkthrough)
  - [1. Install Nessus](#1-install-nessus)
  - [2. Start the Nessus Service](#2-start-the-nessus-service)
  - [3. Complete Initial Web Setup](#3-complete-initial-web-setup)
  - [4. Identify Lab Network Targets](#4-identify-lab-network-targets)
  - [5. Create and Configure the Scan](#5-create-and-configure-the-scan)
  - [6. Launch the Scan and Review Findings](#6-launch-the-scan-and-review-findings)
  - [7. Export the Vulnerability Report](#7-export-the-vulnerability-report)
- [Key Takeaways](#key-takeaways)
- [What Employers Should Notice](#what-employers-should-notice)

---

## Objectives

- Install and initialize Nessus Essentials in a Linux-based lab
- Validate that the Nessus service is running properly
- Discover target hosts on the local virtual network
- Create and launch a basic vulnerability assessment against a Kali Linux target
- Review discovered vulnerabilities and remediation guidance
- Export a professional scan report for documentation purposes

---

## Lab Environment

| Component | Details |
|---|---|
| Scanner Host | Ubuntu |
| Target Host | Kali Linux |
| Network Type | Local virtual lab network |
| Scanner | Nessus Essentials |
| Supporting Tool | Nmap |
| Virtualization | VirtualBox lab environment |

---

## Tools Used

- **Nessus Essentials** – vulnerability scanning and reporting
- **Nmap** – network discovery and host identification
- **Ubuntu Terminal** – package installation and service management
- **Browser-based Nessus UI** – scan configuration, analysis, and reporting

---

## Skills Demonstrated

- Vulnerability management fundamentals
- Linux package installation and service control
- Host discovery and basic reconnaissance
- Scan policy configuration
- Vulnerability triage and remediation review
- Security documentation and reporting

---

## Assessment Workflow

1. Install Nessus from the Ubuntu terminal
2. Start the `nessusd` service and verify it is active
3. Complete Nessus Essentials initialization in the web interface
4. Identify network addressing and locate the Kali target
5. Build a basic scan and configure discovery options
6. Launch the scan and inspect vulnerability results
7. Export a report for documentation and follow-up analysis

---

## Step-by-Step Walkthrough

### 1. Install Nessus

After verifying the package integrity, Nessus was installed from the Ubuntu terminal.

#### Commands Used

```bash
cd
ls
sudo dpkg -i Nessus-10.7.4-ubuntu1404_amd64.deb
```

#### Installation in Progress
<p align="center">
  <img src="https://imgur.com/S4WH61N.png" width="80%" alt="Installing Nessus package from the Ubuntu terminal">
</p>

#### Successful Installation Output
<p align="center">
  <img src="https://imgur.com/NrFhBtS.png" width="80%" alt="Nessus installation completed successfully on Ubuntu">
</p>

---

### 2. Start the Nessus Service

Once installed, the Nessus daemon was started and verified to ensure the scanner was operational.

#### Commands Used

```bash
sudo systemctl start nessusd
sudo systemctl status nessusd
```

#### Service Start and Status Verification
<p align="center">
  <img src="https://imgur.com/ovmNpvD.png" width="80%" alt="Starting the Nessus service and confirming it is active and running">
</p>

After the service starts, Nessus provides a local HTTPS URL that can be opened in a browser to complete setup.

#### Nessus Local Access URL
<p align="center">
  <img src="https://imgur.com/uHw0K0O.png" width="80%" alt="Nessus local web URL displayed in the Ubuntu terminal">
</p>

---

### 3. Complete Initial Web Setup

Because Nessus uses a local self-signed certificate during setup, the browser presents a warning page first. After proceeding, the web-based initialization steps can be completed.

#### Browser Warning and Certificate Bypass
<p align="center">
  <img src="https://imgur.com/yo33RlI.png" width="80%" alt="Browser warning page before accessing the Nessus web interface">
</p>

#### Nessus Welcome Screen
<p align="center">
  <img src="https://imgur.com/th8Fefp.png" width="80%" alt="Nessus welcome page in the browser">
</p>

#### Register for Nessus Essentials
<p align="center">
  <img src="https://imgur.com/vitSLAJ.png" width="80%" alt="Selecting Nessus Essentials during setup">
</p>

#### Skip Registration Form if Already Registered
<p align="center">
  <img src="https://imgur.com/YJWThm6.png" width="80%" alt="Skipping account registration because an activation code was already obtained">
</p>

#### Retrieve Activation Code from Email
<p align="center">
  <img src="https://imgur.com/aDPmWpX.png" width="80%" alt="Tenable email containing the Nessus Essentials activation code">
</p>

#### Enter Activation Code
<p align="center">
  <img src="https://imgur.com/1lYjnTa.png" width="80%" alt="Entering the activation code in the Nessus setup wizard">
</p>

#### Create Nessus Credentials
<p align="center">
  <img src="https://imgur.com/jtGP7ga.png" width="80%" alt="Creating the Nessus username and password">
</p>

#### Plugin Initialization and Download
<p align="center">
  <img src="https://imgur.com/9v0QvSM.png" width="80%" alt="Nessus initializing and downloading plugins">
</p>

<p align="center">
  <img src="https://imgur.com/r9pd14K.png" width="80%" alt="Nessus continuing initialization after plugin download">
</p>

#### Nessus Ready for Use
<p align="center">
  <img src="https://imgur.com/iVymTOE.png" width="80%" alt="Nessus setup completed and ready for use">
</p>

---

### 4. Identify Lab Network Targets

Before scanning, the lab network was reviewed to determine the Ubuntu host addressing information and identify the Kali Linux target.

#### Commands Used

```bash
route
ifconfig
```

#### Review Gateway and Local IP Addressing
<p align="center">
  <img src="https://imgur.com/R5kMq4M.png" width="80%" alt="Reviewing the default gateway and Ubuntu IP addressing from the terminal">
</p>

To locate the Kali system on the same subnet, Nmap host discovery was used.

#### Command Used

```bash
sudo nmap -PR -sn 10.0.2.0/24
```

#### Identify the Kali Host on the Network
<p align="center">
  <img src="https://imgur.com/Y03XZPR.png" width="80%" alt="Using Nmap ping discovery to identify the Kali target host on the subnet">
</p>

---

### 5. Create and Configure the Scan

With the target identified, a new Nessus scan was created using the **Basic Scan** template.

#### Create a New Scan
<p align="center">
  <img src="https://imgur.com/SYVI2N8.png" width="80%" alt="Initializing a new scan in Nessus">
</p>

#### Select the Basic Scan Template
<p align="center">
  <img src="https://imgur.com/Jw775Y3.png" width="80%" alt="Selecting the Basic Scan template in Nessus">
</p>

#### Enter the Scan Name, Description, and Targets
<p align="center">
  <img src="https://imgur.com/UYFGgH1.png" width="80%" alt="Entering the scan details and target IP address in Nessus">
</p>

#### Configure Discovery Options

In this project, the discovery settings were adjusted to scan **all ports**, expanding visibility across the target host.

<p align="center">
  <img src="https://imgur.com/HA26EEk.png" width="80%" alt="Configuring Nessus discovery settings to scan all ports">
</p>

#### Save the Scan Configuration
<p align="center">
  <img src="https://imgur.com/VZVFOqi.png" width="80%" alt="Saving the completed Nessus scan configuration">
</p>

---

### 6. Launch the Scan and Review Findings

Once the configuration was saved, the scan was launched from the Nessus dashboard.

#### Launch the Scan
<p align="center">
  <img src="https://imgur.com/UrCOXRS.png" width="80%" alt="Launching the configured Nessus scan">
</p>

#### Scan Completion Status
<p align="center">
  <img src="https://imgur.com/82fxdOy.png" width="80%" alt="Nessus scan completed successfully with status indicator">
</p>

After completion, the results page provided an overview of discovered issues and available tabs for deeper investigation.

#### Results Overview and Vulnerability Tabs
<p align="center">
  <img src="https://imgur.com/Lk1Pgzo.png" width="80%" alt="Nessus results page showing vulnerability-related tabs">
</p>

#### Drill Down into Individual Vulnerabilities
<p align="center">
  <img src="https://imgur.com/CyYOyMX.png" width="80%" alt="Reviewing detailed vulnerability findings inside Nessus">
</p>

#### Review Description and Remediation Guidance
<p align="center">
  <img src="https://imgur.com/o6ffQNJ.png" width="80%" alt="Viewing the vulnerability description and recommended remediation steps">
</p>

---

### 7. Export the Vulnerability Report

After reviewing the findings, a report was generated from the Nessus interface for documentation and offline review.

#### Open Report Export Options
<p align="center">
  <img src="https://imgur.com/5bCU94K.png" width="80%" alt="Opening the report export options from the vulnerability results page">
</p>

#### Select the Report Format
<p align="center">
  <img src="https://imgur.com/x5mwp7D.png" width="80%" alt="Selecting the report format before generating the Nessus report">
</p>

#### Downloaded Report File
<p align="center">
  <img src="https://imgur.com/e6zlq8o.png" width="80%" alt="Generated Nessus report visible in the downloads folder">
</p>

#### Final Exported Report View
<p align="center">
  <img src="https://imgur.com/AXBDlRw.png" width="80%" alt="Opened Nessus report showing the exported vulnerability assessment results">
</p>

---

## Key Takeaways

- Nessus can be deployed quickly in a Linux-based homelab for realistic vulnerability assessment practice
- Service validation and plugin initialization are critical before beginning scans
- Basic network discovery helps confirm addressing and identify reachable targets before scanning
- Nessus provides both vulnerability details and remediation guidance, which supports analyst learning and documentation
- Exported reports make it easier to communicate findings and preserve assessment results

---

## What Employers Should Notice

This project highlights practical, entry-level security skills that map well to SOC, vulnerability management, and analyst roles:

- Ability to install and operate security tooling in a lab environment
- Comfort working in Linux and using terminal-based administration commands
- Understanding of host discovery, scan configuration, and vulnerability review workflows
- Clear documentation of technical procedures, findings, and output artifacts
- Strong homelab initiative and hands-on learning outside of a classroom-only setting

---

## Final Note

This lab is a foundational vulnerability assessment exercise designed to build familiarity with scanner deployment, target discovery, vulnerability review, and reporting. It can be expanded further by adding authenticated scans, remediation validation, comparison scans, or a formal findings summary section in future iterations.
