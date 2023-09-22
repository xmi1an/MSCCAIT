# Practical-19.md

## Perform enumerate and Hack a Web Application using WPScan and Metasploit

To perform an enumeration and hack a web application using WPScan and Metasploit, follow the step-by-step guide below:

### Step 1: Enumeration with WPScan
1. Install WPScan on your machine if you haven't already. WPScan is a popular WordPress vulnerability scanner.
2. Open the terminal and execute the following command to initiate the WPScan enumeration:

   ```shell
   wpscan --url <target_url>
   ```

   Replace `<target_url>` with the URL of the WordPress website you want to target.

3. WPScan will start enumerating the WordPress installation. It will search for vulnerabilities, usernames, plugins, themes, and other useful information about the website.

### Step 2: Exploitation with Metasploit
1. Install Metasploit on your machine if you haven't already. Metasploit is an exploitation framework that helps discover and exploit vulnerabilities in various applications and systems.
2. Open the terminal and execute the following command to launch Metasploit:

   ```shell
   msfconsole
   ```

3. Inside the Metasploit console, use the `search` command to find an exploit module compatible with the vulnerability identified during the WPScan enumeration. For example, if WPScan discovered a vulnerability related to a plugin, search for an exploit module specific to that plugin:

   ```shell
   search <exploit_module_name>
   ```

   Replace `<exploit_module_name>` with the name or part of the name of the exploit module you want to search for.

4. Once you find the appropriate exploit module, use the `use` command to select it:

   ```shell
   use <exploit_module_name>
   ```

5. Set the required options for the exploit module using the `set` command. You will usually need to set the target URL or IP, port, and other parameters specific to the vulnerability:

   ```shell
   set RHOSTS <target_ip>
   set RPORT <target_port>
   ...
   ```

   Replace `<target_ip>` and `<target_port>` with the IP address and port of the WordPress website you are targeting.

6. Run the exploit using the `exploit` command:

   ```shell
   exploit
   ```

   Metasploit will attempt to exploit the vulnerability and gain access to the target system. If successful, you will be provided with a shell or some form of control over the application.

**Note: It's important to note that performing any unauthorized hacking activities is illegal and unethical. Make sure you have proper authorization and permission before attempting these steps. This guide is for educational purposes only and should not be used to engage in any malicious activities. Always respect the laws and privacy of others.**
