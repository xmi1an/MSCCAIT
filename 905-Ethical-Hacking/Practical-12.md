# Practical-12.md

## Denial-of-Service: Perform Dos and DDoS Attacks using various techniques using Metasploit, hping3, HOIC, and Anti DDoS Guardian

### Step 1: Introduction
In this practical, we will learn how to perform Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS) attacks using various techniques and tools such as Metasploit, hping3, HOIC, and Anti DDoS Guardian.

### Step 2: Understanding DoS and DDoS Attacks
DoS and DDoS attacks are designed to overwhelm a target system or network with a high volume of traffic or resource requests, rendering it unavailable to legitimate users.

### Step 3: Setting up the Environment
Before we begin, make sure you have the following:
- Kali Linux machine (attacker machine)
- Target system or network

### Step 4: Performing DoS Attacks with Metasploit
1. Open a terminal on your Kali Linux machine.
2. Launch the Metasploit Framework by typing `msfconsole` in the terminal.
3. Search for DoS attack modules using the `search` command.
   ```
   search dos
   ```
4. Select an appropriate DoS attack module from the search results.
5. Set the required options for the selected module using the `set` command.
6. Run the DoS attack using the `exploit` command.

### Step 5: Performing DoS Attacks with hping3
1. Open a terminal on your Kali Linux machine.
2. Install hping3 using the following command:
   ```
   sudo apt-get install hping3
   ```
3. Use hping3 to perform a DoS attack on the target system or network. For example, you can send a flood of ICMP packets to the target.
   ```
   sudo hping3 -c <packet_count> -i u1 -S -p <target_port> <target_ip>
   ```
   Replace `<packet_count>` with the number of packets to send, `<target_port>` with the target port number, and `<target_ip>` with the IP address of the target.

### Step 6: Performing DDoS Attacks with HOIC
1. Download and install the HOIC (High Orbit Ion Cannon) tool on your Kali Linux machine.
2. Launch HOIC and enter the target URL or IP address.
3. Configure the attack parameters, such as the attack method, target port, and intensity.
4. Start the DDoS attack by clicking the "Fire" button.

### Step 7: Defending against DoS and DDoS Attacks with Anti DDoS Guardian
1. Install Anti DDoS Guardian on the target system or network.
2. Configure Anti DDoS Guardian to detect and mitigate DoS and DDoS attacks.
3. Monitor the system or network for any suspicious traffic patterns or anomalies.
4. Take appropriate actions to block or mitigate the attack traffic.

### Step 8: Conclusion
In this practical, we have learned how to perform DoS and DDoS attacks using various techniques and tools. We have also explored the importance of defending against such attacks using tools like Anti DDoS Guardian.

