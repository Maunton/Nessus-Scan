# Tenable Nessus Essentials Scan

Performed vulnerability scanning in a lab environment using Nessus Essentials to identify and review host weaknesses.

![Nessus](https://img.shields.io/badge/Vulnerability%20Scanner-Tenable%20Nessus-0C7BDC)
![Platform](https://img.shields.io/badge/Platform-Ubuntu%20%7C%20Kali%20Linux-orange)
![Lab](https://img.shields.io/badge/Environment-VirtualBox-informational)
![Focus](https://img.shields.io/badge/Focus-Vulnerability%20Assessment-red)

## Table of Contents

- [Project Overview](#project-overview)
- [Lab Goals](#lab-goals)
- [Tools and Environment](#tools-and-environment)
- [Install and Start Nessus](#install-and-start-nessus)
- [Prepare the Target Discovery Process](#prepare-the-target-discovery-process)
- [Create and Run the Scan](#create-and-run-the-scan)
- [Review Vulnerabilities](#review-vulnerabilities)
- [Generate the Report](#generate-the-report)
- [Key Takeaways](#key-takeaways)

## Project Overview

This lab demonstrates how Tenable Nessus Essentials can be deployed in a controlled virtual environment to perform vulnerability scanning against a target host. The workflow covers installation, service validation, web setup, target discovery, scan configuration, vulnerability review, and report generation.

This project highlights practical experience with:

- Installing and initializing Nessus Essentials in Ubuntu
- Discovering hosts within a lab subnet
- Configuring a basic vulnerability assessment scan
- Reviewing findings and remediation guidance
- Exporting a scan report for documentation and analysis

## Lab Goals

- Deploy Nessus Essentials in a lab environment
- Verify the scanner service is running properly
- Identify target systems on the local subnet
- Run a vulnerability scan against a Kali Linux host
- Review findings and recommended fixes
- Export a formal assessment report

## Tools and Environment

### Tools Used

- Tenable Nessus Essentials
- Nmap
- Ubuntu Terminal
- Web Browser

### Environment Used

- VirtualBox
- Ubuntu
- Kali Linux

## Install and Start Nessus

After confirming the package integrity, Nessus was installed from the Ubuntu terminal.

### Commands Used

```bash
cd
ls
sudo dpkg -i Nessus-10.7.4-ubuntu1404_amd64.deb
```

### Installation Screenshot

![Nessus package installation](https://imgur.com/S4WH61N.png)

### Post-Installation View

After the package installation completes, Nessus is installed on the Ubuntu system.

![Post-installation output](https://imgur.com/NrFhBtS.png)

### Start the Nessus Service

Open a new Ubuntu terminal and start the Nessus daemon. Then confirm that the service is actively running.

```bash
sudo systemctl start nessusd
sudo systemctl status nessusd
```

![Starting and validating nessusd service](https://imgur.com/ovmNpvD.png)

### Open the Nessus Web Interface

Copy the local Nessus link shown in the terminal and paste it into your browser.

![Nessus local access URL](https://imgur.com/uHw0K0O.png)

### Accept the Browser Warning

Because Nessus uses a local certificate during setup, the browser may show a warning. Continue to the site to access the setup wizard.

![Browser security warning](https://imgur.com/yo33RlI.png)

### Continue Through the Setup Wizard

When the welcome page appears, proceed to the next step.

![Nessus welcome page](https://imgur.com/th8Fefp.png)

### Select Nessus Essentials

Choose **Register for Nessus Essentials** to continue the free lab setup.

![Nessus Essentials selection](https://imgur.com/vitSLAJ.png)

### Skip Registration if Already Completed

If registration has already been completed, choose the option to skip that step.

![Skip registration step](https://imgur.com/YJWThm6.png)

### Retrieve the Activation Code

Open the email sent by Tenable and copy the activation code.

![Activation email](https://imgur.com/aDPmWpX.png)

### Enter the Activation Code

Paste the activation code into Nessus and continue.

![Activation code entry](https://imgur.com/1lYjnTa.png)

### Create Login Credentials

Create a username and password for the Nessus web console.

![Create Nessus account credentials](https://imgur.com/jtGP7ga.png)

### Wait for Plugin Initialization

Nessus will initialize and download plugins before the scanner becomes available.

![Plugin download stage](https://imgur.com/9v0QvSM.png)

### Complete Initialization

Allow Nessus to finish its remaining initialization tasks.

![Initialization progress](https://imgur.com/r9pd14K.png)

### Ready State

Once setup is complete, Nessus is ready for scanning operations.

![Nessus ready state](https://imgur.com/iVymTOE.png)

## Prepare the Target Discovery Process

Before launching a scan, identify the scanner's network context and locate the target host.

### Check the Default Gateway and Ubuntu IP Address

```bash
route
ifconfig
```

![Ubuntu network details](https://imgur.com/R5kMq4M.png)

### Discover the Kali Target Host

Use Nmap to identify live hosts on the subnet and determine the IP address of the Kali system.

```bash
sudo nmap -PR -sn 10.0.2.0/24
```

![Nmap host discovery](https://imgur.com/Y03XZPR.png)

## Create and Run the Scan

### Initialize a New Scan

After identifying the target system, create a new Nessus scan.

![Initialize new scan](https://imgur.com/SYVI2N8.png)

### Choose the Basic Scan Template

For this lab, the **Basic Scan** template is used to assess the Kali machine.

![Basic scan template selection](https://imgur.com/Jw775Y3.png)

### Define the Scan Details

Enter the scan name, description, and target IP address.

![Scan configuration fields](https://imgur.com/UYFGgH1.png)

### Configure Port Discovery

In the discovery settings, configure the scan to check all ports.

![All ports discovery setting](https://imgur.com/HA26EEk.png)

### Save the Scan

After the settings are configured, save the scan profile.

![Save the configured scan](https://imgur.com/VZVFOqi.png)

### Launch the Scan

Start the vulnerability scan from the scan dashboard.

![Launch the Nessus scan](https://imgur.com/UrCOXRS.png)

### Confirm Completion

When the check mark appears, the scan has finished and the results are ready to review.

![Completed scan status](https://imgur.com/82fxdOy.png)

## Review Vulnerabilities

### Open the Results Tabs

The completed scan provides multiple tabs, including the vulnerability summary.

![Scan results overview](https://imgur.com/Lk1Pgzo.png)

### Review Detailed Findings

Open the vulnerabilities tab and select individual findings to review additional context.

![Detailed vulnerability list](https://imgur.com/CyYOyMX.png)

### Examine Recommended Fixes

Each finding includes a description of the issue and remediation guidance.

![Vulnerability description and solution](https://imgur.com/o6ffQNJ.png)

## Generate the Report

### Return to the Main Vulnerabilities Page

Navigate back to the main scan page to export a report.

![Return to report export page](https://imgur.com/5bCU94K.png)

### Generate the Report

Select the desired report format and generate the export.

![Generate report options](https://imgur.com/x5mwp7D.png)

### Locate the Downloaded File

The report can be found in the downloads folder.

![Downloaded report location](https://imgur.com/e6zlq8o.png)

### Review the Final Report

Open the exported file to review the assessment results.

![Opened Nessus report](https://imgur.com/AXBDlRw.png)

## Key Takeaways

This project demonstrates hands-on vulnerability assessment workflow knowledge, including scanner deployment, target discovery, scan execution, result review, and reporting. It also shows familiarity with:

- Working in a virtualized security lab
- Using Nmap to identify systems prior to scanning
- Reviewing host weaknesses through Nessus findings
- Interpreting remediation guidance from scan results
- Documenting security work in a repeatable format

