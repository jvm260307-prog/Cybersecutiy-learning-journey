# Tab, Tab, Attack

## Challenge Information

### - Platform: CyLab Security Academy
### - CTF: picoCTF 2021
### - Challenge Name: Tab, Tab, Attack
### - Category: General Skills
### - Difficulty: Easy

## Objective

Download and extract the provided ZIP archive, navigate through its nested directories, locate the hidden flag, and retrieve it using Linux command-line tools.

## Concepts Learned

### - ZIP archive extraction
### - Nested directory navigation
### - Linux tab completion
### - File identification
### - Extracting readable text from binary files
### - Using "strings" and "grep" to search for a flag

## Tools Used

### - Linux terminal / CyLab WebShell
### - "unzip"
### - "cd", "ls", "find"
### - "file"
### - "strings"
### - "grep"

## Solution

## Step 1: Download the Challenge Archive

The challenge provided a ZIP archive named "Addadshashanammu.zip".

After downloading it, I moved to the directory containing the archive and extracted its contents.

unzip Addadshashanammu.zip

The archive contained a series of nested directories and files. The flag was not immediately visible in the initial directory.

## Step 2: Navigate Through the Nested Directories

The challenge hint mentioned solving the problem with repeated Tab key presses. This refers to shell tab completion, which helps complete directory and file names without typing every character.

I used the following commands to inspect the extracted contents:

### ls

To enter a directory:

### cd directory_name

To inspect the current location:

### pwd

I continued exploring the nested directory structure until I reached the file containing the flag.

Tab completion can make this process easier. For example, type the first few characters of a directory name and press "Tab" to complete it. If several names match, pressing "Tab" again may display the available choices.

## Step 3: Locate the Final File

Instead of manually opening every file, Linux provides commands that can help identify files and their locations.

### find . -type f

This lists files within the current directory and its subdirectories.

To identify the type of a particular file:

file filename

The final file was not a normal text document. It contained binary data, which explains why opening it directly in Windows Notepad produced unusual characters and symbols.

## Step 4: Extract Readable Text from the Binary File

A useful Linux utility for this situation is "strings". It searches a binary file for sequences of printable characters.

strings filename

To narrow the output and look for a flag-like string:

strings filename | grep -i academy

Here:

- "strings" extracts readable text from the file.
- "|" pipes the output into another command.
- "grep -i academy" searches for text containing "academy", without distinguishing uppercase and lowercase letters.

This revealed the flag embedded in the binary file.

## Step 5: Retrieve the Flag

The flag recovered from the file was:

## academy{13v3l_up!_t4k3_4_r35t!_9d928112}

I copied the flag into the challenge submission field and submitted it.

## Linux Commands Used

Command| Purpose
"unzip"| Extract the ZIP archive
"ls"| List files and directories
"cd"| Change the current directory
"pwd"| Display the current directory path
"find . -type f"| Locate files recursively
"file"| Identify a file's format
"strings"| Extract readable character sequences from binary data
"grep -i"| Search text without case sensitivity
"Tab"| Complete file and directory names in the shell

## Why Notepad Displayed Unreadable Characters

The final file contained binary data rather than ordinary text. Notepad attempted to interpret those bytes as text, resulting in unusual symbols and characters.

This does not necessarily mean the file is corrupted. A binary file may contain readable strings alongside non-text data. The "strings" utility can extract those readable portions without trying to display the entire file as a text document.

## Key Takeaways

This challenge taught me how to navigate nested directories efficiently, use shell tab completion, identify files, and inspect binary data for hidden information.

I also learned that a file does not need to be a text document to contain a readable flag. Linux tools such as "file" and "strings" can reveal useful information that may not be apparent when opening a file in a graphical text editor.

## Challenge Source

"CyLab Security Academy — Tab, Tab, Attack" 

## Flag

"academy{13v3l_up!_t4k3_4_r35t!_9d928112}"

## Evidence

![CTF solution screenshot 1](https://github.com/user-attachments/assets/d7150a91-dd7c-4469-8e50-e9053e61acea
)

![CTF solution screenshot 2](https://github.com/user-attachments/assets/fb0a589d-04bb-4499-b06c-cd045351212a
)
