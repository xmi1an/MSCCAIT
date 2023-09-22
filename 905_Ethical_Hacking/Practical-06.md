# Practical 06: Hack a Windows Machine with a Malicious Office Document using TheFatRat

In this practical, we will hack a Windows machine using a malicious Office document created with TheFatRat.

## Step 1: Setting up TheFatRat

1. Open your terminal and type in the following command to clone the TheFatRat repository: `git clone https://github.com/Screetsec/TheFatRat.git`
2. Navigate to the TheFatRat directory using the command: `cd TheFatRat`
3. Run the setup script with the command: `chmod +x setup.sh && ./setup.sh`

## Step 2: Creating a Malicious Office Document

1. In the TheFatRat menu, select the option to create a malicious Office document.
2. Follow the prompts to set the payload, LHOST, LPORT, and filename.
3. Once the document is created, it will be saved in the TheFatRat directory.

## Step 3: Delivering the Malicious Document

1. Use a method of your choice to deliver the malicious document to the target Windows machine. This could be via email, file transfer, or social engineering.
2. Once the target opens the document, a Meterpreter session will be created.

## Step 4: Exploiting the Target Machine

1. In your terminal, type `sessions` to see a list of active Meterpreter sessions.
2. Connect to the session corresponding to your target with the command `sessions -i ID`, replacing "ID" with the session ID.
3. You now have control over the target machine and can execute commands, download files, and more.

Remember to use this knowledge responsibly and only for ethical hacking purposes.

