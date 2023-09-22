# Practical-15.md

## Perform footprint the Web Server using various tools like, Ghost Eye, Skipfish etc.

### Step 1: Introduction
In this practical, we will learn how to perform footprinting on a web server using various tools like Ghost Eye and Skipfish.

### Step 2: Understanding Footprinting
Footprinting is the process of gathering information about a target system or network. In the context of web servers, footprinting involves collecting information about the server's operating system, software versions, and other relevant details.

### Step 3: Setting up the Environment
Before we begin, make sure you have the following:
- Kali Linux machine (attacker machine)
- Target web server

### Step 4: Using Ghost Eye
1. Open a terminal on your Kali Linux machine.
2. Install Ghost Eye using the following command:
   ```
   sudo apt-get install ghost-eye
   ```
3. Launch Ghost Eye by typing `ghost-eye` in the terminal.
4. Enter the IP address or domain name of the target web server.
5. Ghost Eye will perform a footprinting scan and display the results.

### Step 5: Using Skipfish
1. Open a terminal on your Kali Linux machine.
2. Install Skipfish using the following command:
   ```
   sudo apt-get install skipfish
   ```
3. Launch Skipfish by typing `skipfish` in the terminal.
4. Enter the URL of the target web server.
5. Skipfish will perform a comprehensive scan of the web server and generate a report.

### Step 6: Analyzing the Results
1. Review the results obtained from Ghost Eye and Skipfish.
2. Look for vulnerabilities or weaknesses in the web server's configuration.
3. Use the information gathered to plan further attacks or security measures.

### Step 7: Defending Against Footprinting
1. As a web server administrator, it is important to regularly perform footprinting scans on your own server.
2. Identify and patch any vulnerabilities or weaknesses discovered during the scan.
3. Implement security measures such as firewall rules, intrusion detection systems, and regular software updates to protect against footprinting attacks.

By following these steps, you will be able to perform footprinting on a web server using tools like Ghost Eye and Skipfish.

