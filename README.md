
<h1>Tenable Nessus Essentials Scan</h1>



<h2>Description</h2>
This project entails deploying and configuring Nessus Essentials on Ubuntu, executed through the command line interface within VirtualBox. Using Ubuntu CLI tools, we will map the network and utilize Nessus to scan and assess Kali Linux for vulnerabilities.




<br />


<h2>Tools and Commands</h2>

- <b>Nessus Essentials</b>
- <b>sha256sum</b>
- <b>route</b>
- <b>ifconfig</b>
- <b>nmap</b>

<h2>Environments and Machines</h2>

- <b>VirtualBox VM</b>
- <b>Kali Linux</b>
- <b>Ubuntu 22.04</b>

<h1>Project walk-through:</h1>
  
<h2>Download Nessus from www.tenable.com/products/nessus/nessus-essentials:</h2>

<br />

<h3>Fill out the 'Register for an Activation Code' and click 'Get Started':</h3>
<p align="center">
<img src="https://imgur.com/U8trQNm.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Click the 'Download' link:</h3>
<p align="center">
<img src="https://imgur.com/PL0BOqW.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Choose your platform and click Download:</h3>
<p align="center">
<img src="https://imgur.com/CGVd31V.png" height="80%" width="80%" alt="Project walk-through"/>
<br />
<br />
<h3>Open the command line terminal in Ubuntu and check/compare the sha256 hash values for file integrity:</h3>
Pro Tip: After typing 'sha256sum Downloads/N' hit the tab key to autofill the rest <br/>
  
  ## Usage:
    sha256sum Downloads/Nessus-10.7.4-ubuntu1404_amd64.deb 
<p align="center"> 
<img src="https://imgur.com/4CK49vY.png" height="80%" width="80%" alt="Project walk-through"/> 
<br />
<br />
<h3>Install the download package:</h3>
Change directory(cd) into the Downloads/ folder, list contents(ls) and install the Nessus package <br/>
  
 ## Usage:
    cd
    ls
    sudo dpkg -i Nessus-10.7.4-ubuntu1404_amd64.deb
  
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
