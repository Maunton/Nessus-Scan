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
- [Download and Prepare Nessus](#download-and-prepare-nessus)
- [Install and Start Nessus](#install-and-start-nessus)
- [Prepare the Target Discovery Process](#prepare-the-target-discovery-process)
- [Create and Run the Scan](#create-and-run-the-scan)
- [Review Vulnerabilities](#review-vulnerabilities)
- [Generate the Report](#generate-the-report)
- [Key Takeaways](#key-takeaways)

## Project Overview

This lab demonstrates how Tenable Nessus Essentials can be deployed in a controlled virtual environment to perform vulnerability scanning against a target host. The workflow covers package download, integrity verification, installation, service validation, web setup, target discovery, scan configuration, vulnerability review, and report generation.

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

## Download and Prepare Nessus

### 1. Nessus Download Page

![Nessus download page](images/01-nessus-download-page.png)

### 2. Download Options

![Nessus download options](images/02-nessus-download-options.png)

### 3. Package Downloaded

![Nessus package downloaded](images/03-nessus-package-downloaded.png)

### 4. Package Integrity Verification

![Package integrity verification](images/04-package-integrity-verification.png)

## Install and Start Nessus

After confirming the package integrity, Nessus was installed from the Ubuntu terminal.

### Commands Used

```bash
cd
ls
sudo dpkg -i Nessus-10.7.4-ubuntu1404_amd64.deb
```

### 5. Nessus Package Installation

![Nessus package installation](images/05-nessus-package-installation.png)

### 6. Post-Installation Output

![Post-installation output](images/06-post-installation-output.png)

### Start the Nessus Service

Open a new Ubuntu terminal and start the Nessus daemon. Then confirm that the service is actively running.

```bash
sudo systemctl start nessusd
sudo systemctl status nessusd
```

### 7. Start `nessusd` Service

![Start nessusd service](images/07-start-nessusd-service.png)

### 8. Nessus Local Access URL

Copy the local Nessus link shown in the terminal and paste it into your browser.

![Nessus local access URL](images/08-nessus-local-access-url.png)

### 9. Browser Security Warning

Because Nessus uses a local certificate during setup, the browser may show a warning. Continue to the site to access the setup wizard.

![Browser security warning](images/09-browser-security-warning.png)

### 10. Nessus Welcome Page

When the welcome page appears, proceed to the next step.

![Nessus welcome page](images/10-nessus-welcome-page.png)

### 11. Register Nessus Essentials

Choose **Register for Nessus Essentials** to continue the free lab setup.

![Register Nessus Essentials](images/11-register-nessus-essentials.png)

### 12. Skip Registration Step

If registration has already been completed, choose the option to skip that step.

![Skip registration step](images/12-skip-registration-step.png)

### 13. Tenable Activation Email

Open the email sent by Tenable and copy the activation code.

![Tenable activation email](images/13-tenable-activation-email.png)

### 14. Enter Activation Code

Paste the activation code into Nessus and continue.

![Enter activation code](images/14-enter-activation-code.png)

### 15. Create Nessus Login

Create a username and password for the Nessus web console.

![Create Nessus login](images/15-create-nessus-login.png)

### 16. Plugin Download Initializing

Nessus will initialize and download plugins before the scanner becomes available.

![Plugin download initializing](images/16-plugin-download-initializing.png)

### 17. Plugin Initialization Progress

Allow Nessus to finish its remaining initialization tasks.

![Plugin initialization progress](images/17-plugin-initialization-progress.png)

### 18. Nessus Ready Dashboard

Once setup is complete, Nessus is ready for scanning operations.

![Nessus ready dashboard](images/18-nessus-ready-dashboard.png)

## Prepare the Target Discovery Process

Before launching a scan, identify the scanner's network context and locate the target host.

### Check the Default Gateway and Ubuntu IP Address

```bash
route
ifconfig
```

### 19. Ubuntu Network Details

![Ubuntu network details](images/19-ubuntu-network-details.png)

### Discover the Kali Target Host

Use Nmap to identify live hosts on the subnet and determine the IP address of the Kali system.

```bash
sudo nmap -PR -sn 10.0.2.0/24
```

### 20. Nmap Host Discovery

![Nmap host discovery](images/20-nmap-host-discovery.png)

## Create and Run the Scan

### 21. Create New Scan

After identifying the target system, create a new Nessus scan.

![Create new scan](images/21-create-new-scan.png)

### 22. Basic Scan Template

For this lab, the **Basic Scan** template is used to assess the Kali machine.

![Basic scan template](images/22-basic-scan-template.png)

### 23. Scan Name, Description, and Targets

Enter the scan name, description, and target IP address.

![Scan name description targets](images/23-scan-name-description-targets.png)

### 24. All Ports Discovery Settings

In the discovery settings, configure the scan to check all ports.

![All ports discovery settings](images/24-all-ports-discovery-settings.png)

### 25. Save Scan Configuration

After the settings are configured, save the scan profile.

![Save scan configuration](images/25-save-scan-configuration.png)

### 26. Launch Scan

Start the vulnerability scan from the scan dashboard.

![Launch scan](images/26-launch-scan.png)

### 27. Scan Completed, Results Ready

When the check mark appears, the scan has finished and the results are ready to review.

![Scan completed results ready](images/27-scan-completed-results-ready.png)

## Review Vulnerabilities

### 28. Scan Results Vulnerability Tabs

The completed scan provides multiple tabs, including the vulnerability summary.

![Scan results vulnerability tabs](images/28-scan-results-vulnerability-tabs.png)

### 29. Detailed Vulnerability List

Open the vulnerabilities tab and select individual findings to review additional context.

![Detailed vulnerability list](images/29-detailed-vulnerability-list.png)

### 30. Vulnerability Description and Fix

Each finding includes a description of the issue and remediation guidance.

![Vulnerability description and fix](images/30-vulnerability-description-and-fix.png)

## Generate the Report

### 31. Report Export Page

Navigate back to the main scan page to export a report.

![Report export page](images/31-report-export-page.png)

### 32. Generate Report Options

Select the desired report format and generate the export.

![Generate report options](images/32-generate-report-options.png)

### 33. Downloaded Report File

The report can be found in the downloads folder.

![Downloaded report file](images/33-downloaded-report-file.png)

### 34. Opened Nessus Report

Open the exported file to review the assessment results.

![Opened Nessus report](images/34-opened-nessus-report.png)

## Key Takeaways

This project demonstrates hands-on vulnerability assessment workflow knowledge, including scanner deployment, target discovery, scan execution, result review, and reporting. It also shows familiarity with:

- Working in a virtualized security lab
- Using Nmap to identify systems prior to scanning
- Reviewing host weaknesses through Nessus findings
- Interpreting remediation guidance from scan results
- Documenting security work in a repeatable format
