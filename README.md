# Scanning-A-Network-with-Nessus

## Project Goal:
Perform a network vulnerability scan on Metasploitable 2 using Nessus to identify potential security issues.

## Preparation

### Setting Up the Environment
Begin by setting up the necessary software and ensuring all dependencies are installed. This guide assumes you're using Kali Linux for the scanning machine and Metasploitable 2 as the target machine.

1. **Install Metasploitable 2**:
   - Download Metasploitable 2 from [SourceForge](https://sourceforge.net/projects/metasploitable/).
   - Import the Metasploitable 2 virtual machine into VirtualBox. We'll be using the Debian 64bit.
  
  ![Screenshot 2024-06-13 202923](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/bdafba7b-ff4b-4c52-bc32-1acc9da5353c)

2. **Install Nessus**:
   - Download Nessus from [Tenable's website](https://www.tenable.com/products/nessus).
   - Follow the installation instructions specific to your Linux distribution.
   
![Screenshot 2024-06-13 203018](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/efa02b06-b5f3-490b-8aac-60287e40b6f0)

3. **Start Nessus Service**:
   - On Kali Linux, start the Nessus service with:
     ```bash
     systemctl start nessusd.service
     ```

     ![Screenshot 2024-06-13 013138](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/f7ab7aa2-46fd-4f2a-8274-71296abedf00)


4. **Access Nessus**:
   - Open a web browser and navigate to `https://localhost:8834`.
   - Follow the setup wizard to create an account and log in.
  
   
![Screenshot 2024-06-13 210325](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/b9823c10-cd68-4de1-81c5-d68df092a702)


## Scanning Metasploitable 2 with Nessus

### Step-by-Step Guide

1. **Find the IP Address of Metasploitable 2**:
   - Open a terminal in Metasploitable 2.
   - Run the `ifconfig` command to find the IP address of the Metasploitable 2 VM.
     ```bash
     ifconfig
     ```
   - Note down the IP address (e.g., `192.168.1.100`).

   ![Screenshot 2024-06-13 014118](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/aec940d8-c20d-4fd1-b92b-19586372b239)


2. **Create a New Scan**:
   - Click on the `New Scan` button.
   - Choose the `Basic Network Scan` template.
   

![Screenshot 2024-06-13 212340](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/ccf01106-2df0-4ecb-ae10-f05c29ccd48f)



3. **Configure the Scan**:
   - Name your scan (e.g., "Metasploitable 2 Scan").
   - Set the target to the IP address of your Metasploitable 2 VM.

 
![Screenshot 2024-06-13 212249](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/ddfb30dc-a5a6-4aa6-acf7-f7fd43e16f79)


4. **Launch the Scan**:
   - Save the scan configuration.
   - Click the `Launch` button to start the scan.


5. **Monitor the Scan Progress**:
   - The scan will take some time to complete. You can monitor its progress on the Nessus dashboard.


6. **Review the Scan Results**:
   - Once the scan is complete, click on the completed scan to view the results.
   - Nessus will display a list of vulnerabilities found on the Metasploitable 2 machine, categorized by severity.

![Screenshot 2024-06-13 212449](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/06dc1d75-302f-44bf-9e25-57356c101e07)


### Interpreting the Results
- **High Severity**: These are critical vulnerabilities that should be addressed immediately. Examples might include unpatched software or configuration issues that could be exploited remotely.
- **Medium Severity**: These are less critical but still pose a significant risk. They might include outdated software versions or minor configuration issues.
- **Low Severity**: These are minor vulnerabilities that could potentially be exploited but are less likely to cause significant harm.

![Screenshot 2024-06-13 212643](https://github.com/jeffreyamunoz/Scanning-A-Network-with-Nessus/assets/172007477/cd2f7389-fbfc-44fe-bc82-c9562166d07b)


## Summary

Conducting a network vulnerability scan with Nessus helps identify potential security issues within a network. By scanning Metasploitable 2, we gain hands-on experience with vulnerability assessment tools, allowing us to understand the types of vulnerabilities that exist and how they can be mitigated.

As cybersecurity professionals, it's crucial to regularly scan and assess the security posture of systems within a network to proactively identify and address vulnerabilities before they can be exploited by malicious actors. This exercise is for educational purposes only. Always ensure you have authorization before scanning any network or system.
