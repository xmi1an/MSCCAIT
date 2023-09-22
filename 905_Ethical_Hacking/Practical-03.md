# Practical 03: Perform Scanning/Enumeration/Vulnerability Analysis

In this practical, we will perform scanning, enumeration, and vulnerability analysis using various tools and techniques.

## Step 1: Using NMAP for Host/Port/Service Discovery

1. Open your terminal and type in the following command to perform a basic NMAP scan: `nmap -v -A target_ip`
2. Analyze the scan results for any open ports, running services, and their versions.

## Step 2: Using Hping3

1. In your terminal, type in the following command to perform a SYN scan with Hping3: `hping3 -S target_ip -p ++80`
2. Analyze the scan results for any useful information.

## Step 3: Using Colasoft Packet Builder

1. Download and install Colasoft Packet Builder from the official website.
2. Open the program and create a new packet. Set the packet parameters as per your requirements.
3. Send the packet to your target and analyze the response.

## Step 4: Using Metasploit Framework

1. Open your terminal and type in the following command to start Metasploit: `msfconsole`
2. Use the `search` command to find a suitable exploit for your target based on the information gathered in the previous steps.
3. Set the exploit parameters and run the exploit.

By following these steps, we can identify potential vulnerabilities in our target system, which can be exploited in later stages of an ethical hacking operation.
