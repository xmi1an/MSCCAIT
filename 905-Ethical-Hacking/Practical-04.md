# Practical 04: System Hacking: Perform active online attack to crack the System’s password using Responder

In this practical, we will perform an active online attack to crack the system's password using Responder.

## Step 1: Setting up Responder

1. Open your terminal and type in the following command to clone the Responder repository: `git clone https://github.com/lgandx/Responder.git`
2. Navigate to the Responder directory using the command: `cd Responder`

## Step 2: Configuring Responder

1. Open the Responder.conf file in a text editor.
2. Set the parameters as per your requirements. For example, you can set `SMB = On` to enable SMB spoofing.

## Step 3: Running Responder

1. In your terminal, type in the following command to start Responder: `sudo python Responder.py -I eth0`
2. Replace `eth0` with the name of your network interface.

## Step 4: Performing the Attack

1. Wait for a target system to send a network request.
2. Responder will intercept the request and send a fake response, tricking the target system into sending its login credentials.
3. Responder will capture the login credentials and display them in the terminal.

By following these steps, we can perform an active online attack to crack a system's password using Responder. This can be a powerful tool in an ethical hacking operation, but it should be used responsibly and legally.
