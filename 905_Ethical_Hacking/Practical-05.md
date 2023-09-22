# Practical 05: System Hacking: Gain access to a Remote System using Armitage/Metasploit Framework

In this practical, we will gain access to a remote system using Armitage and the Metasploit Framework.

## Step 1: Setting up Armitage

1. Open your terminal and type in the following command to install Armitage: `sudo apt-get install armitage`
2. Once the installation is complete, start Armitage with the command: `armitage`

## Step 2: Setting up Metasploit Framework

1. In your terminal, type in the following command to clone the Metasploit Framework repository: `git clone https://github.com/rapid7/metasploit-framework.git`
2. Navigate to the Metasploit Framework directory using the command: `cd metasploit-framework`
3. Install the necessary dependencies with the command: `bundle install`
4. Start the Metasploit Framework with the command: `./msfconsole`

## Step 3: Gaining Access to a Remote System

1. In Armitage, click on "Hosts" and then "Nmap Scan" to scan for potential targets.
2. Once you have identified a target, right-click on it and select "Attack" to view the available exploits.
3. Choose an exploit and configure it as necessary. Click "Launch" to start the attack.
4. If the attack is successful, you will gain access to the remote system.

Remember to always use these tools responsibly and only on systems you have permission to access.
