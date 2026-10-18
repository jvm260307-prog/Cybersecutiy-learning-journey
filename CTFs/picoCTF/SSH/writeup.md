# SSH

## Challenge Information

### - Platform: CyLab Security Academy
### - CTF: picoCTF
### - Challenge Name: SSH
### - Category: General Skills
### - Difficulty: Easy

## Objective

Connect to the remote challenge server using Secure Shell (SSH), authenticate with the provided credentials, and retrieve the flag.

## Concepts Learned

- Secure Shell (SSH)
- Remote server authentication
- Specifying a custom SSH port
- Basic Linux terminal commands
- Reading files from a remote machine

## Tools Used

### - Linux terminal / CyLab WebShell
### - SSH client

## Solution

### Step 1: Understand the Challenge

The challenge provides a remote server, a username, a port number, and a password. The goal is to establish an SSH connection and locate the flag on the remote machine.

SSH allows us to securely access and execute commands on another computer over a network.

### Step 2: Connect to the Server

The challenge specifies the following connection details:

- Username: "ctf-player"
- Hostname: "xebeo.cylabacademy.net"
- Port: "10400"
- Password: Use the password displayed on the challenge page.

Run the following command in the terminal:

## ssh -p 10400 ctf-player@xebeo.cylabacademy.net

If prompted to confirm the server's fingerprint, verify that this is the expected challenge server and type "yes" to continue.

When prompted for the password, enter the password provided by the challenge. The terminal may not display any characters while you type; this is normal.

### Step 3: Explore the Remote Machine

After successfully connecting, use basic Linux commands to inspect the remote environment.

## pwd

Displays the current working directory.

## ls

Lists files and directories in the current location.

## ls -la

Lists files, including hidden files.

## Step 4: Locate and Read the Flag

Inspect the files in the directory and identify the file containing the flag. If the challenge file is named "flag", read it using:

## cat flag

If the flag is stored in a different file, replace "flag" with the appropriate filename.

Copy the flag displayed in the terminal and submit it on the challenge page.

## Step 5: Exit the SSH Session

Once the flag has been retrieved, leave the remote server:

## exit

This closes the SSH session and returns you to your local terminal.

### Linux Commands Used

Command| Purpose
"ssh -p"| Connect to a remote server using a specified port
"pwd"| Display the current directory
"ls"| List directory contents
"ls -la"| Show all files, including hidden files
"cat"| Display the contents of a file
"exit"| End the remote shell session

## Key Takeaways

This challenge demonstrated how SSH can be used to securely access a remote Linux machine. I learned how to specify a non-default port, authenticate using challenge credentials, explore a remote filesystem, and retrieve a flag using basic shell commands.

Challenge Source

"CyLab Security Academy — SSH Challenge" 

"CyLab Security Academy — The Shell Primer" (https://primer.cylabacademy.org/#_the_shell)

## Flag  (academy{ssh7f2a9c81})

## Evidence

![CTF solution screenshot 1](https://github.com/user-attachments/assets/5747fcb3-bb1a-454b-bf35-f44759e1f9ef
)

![CTF solution screenshot 2](https://github.com/user-attachments/assets/18ac7cdb-8fc3-46b1-9386-507fc3e240da
)
