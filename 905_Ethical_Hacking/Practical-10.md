# Practical-10.md

## Sniffing: Perform Packet-Sniffing techniques, discover Network Vulnerabilities, Defend against Sniffing Attacks using wireshark

### Step 1: Introduction
In this practical, we will learn how to perform packet-sniffing techniques, discover network vulnerabilities, and defend against sniffing attacks using Wireshark.

### Step 2: Setting up the Environment
Before we begin, make sure you have the following:
- Kali Linux machine (attacker machine)
- Target network (can be a virtual network or a physical network)

### Step 3: Installing Wireshark
1. Open a terminal on your Kali Linux machine.
2. Install Wireshark using the following command:
   ```
   sudo apt-get install wireshark
   ```

### Step 4: Capturing Packets
1. Launch Wireshark by typing `wireshark` in the terminal.
2. Select the network interface you want to capture packets from.
3. Click on the "Start" button to begin capturing packets.

### Step 5: Analyzing Captured Packets
1. Once packets are captured, Wireshark will display them in a list.
2. Use the various filters and analysis tools provided by Wireshark to analyze the captured packets.
   - Filter packets based on protocols, source/destination IP addresses, ports, etc.
   - Analyze packet headers, payloads, and other details.
   - Identify network vulnerabilities, such as unencrypted passwords, sensitive information leakage, etc.

### Step 6: Defending against Sniffing Attacks
1. To defend against sniffing attacks, it is important to secure the network and encrypt sensitive data.
2. Use encryption protocols such as SSL/TLS for secure communication.
3. Implement network security measures, such as firewalls, intrusion detection systems, etc.
4. Regularly monitor network traffic for any suspicious activities using tools like Wireshark.

### Step 7: Cleanup
After completing the packet analysis, it is important to close Wireshark and clean up the captured packets. Use the following steps:
1. Click on the "Stop" button in Wireshark to stop capturing packets.
2. Save the captured packets if required.
3. Close Wireshark.

### Conclusion
In this practical, we learned how to perform packet-sniffing techniques, discover network vulnerabilities, and defend against sniffing attacks using Wireshark. It is important to use these techniques responsibly and only for ethical purposes.

---

That's it for Practical-10. Stay tuned for the next practical!

