# **picoCTF Challenge Writeup: Verify**

## **Challenge Overview**  
This challenge involves connecting to a remote instance via SSH, identifying an encrypted file containing the flag, and decrypting it using a provided script. A checksum is given as a clue to locate the correct file.  
---

### **Description**
- People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
#### Hints:
1. Checksums let you tell if a file is complete and from the original distributor. If the hash doesn't match, it's a different file.
2. You can create a SHA checksum of a file with sha256sum <file> or all files in a directory with sha256sum <directory>/*.
3. Remember you can pipe the output of one command to another with |. Try practicing with the 'First Grep' challenge if you're stuck!

---

## **Step-by-Step Walkthrough**

### **Step 1: Connecting to the Remote Instance**
1. Use the provided SSH credentials to access the remote machine:
   ```bash
   ssh -p ctf-player@rhea.picoctf.net
   ```
2. Once connected, list the files in the directory:
   ```bash
   ls -la
   ```
   You should see the following files:
   - `checksum.txt` (contains the target SHA-256 hash)
   - `decrypt.sh` (script to decrypt files)
   - `files/` (directory containing multiple encrypted files)

### **Step 2: Identifying the Target File**
1. View the contents of `checksum.txt` to retrieve the provided SHA-256 hash:
   ```bash
   cat checksum.txt
   ```
   Example output:
   ```
   d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2d2
   ```
2. Generate SHA-256 hashes for all files in the `files/` directory:
   ```bash
   sha256sum files/*
   ```
3. Use `grep` to find the file that matches the checksum:
   ```bash
   sha256sum files/* | grep $(cat checksum.txt)
   ```
   This command filters the hash list and identifies the correct file.

### **Step 3: Decrypting the File**
1. Use the `decrypt.sh` script to decrypt the identified file:
   ```bash
   ./decrypt.sh files/<identified_file>
   ```
2. If necessary, provide execution permissions to the script:
   ```bash
   chmod +x decrypt.sh
   ```
3. Run the script again if needed.

### **Step 4: Retrieving the Flag**
- The decrypted file should reveal the flag in the format `picoCTF{...}`.
- Example output:
  ```
  picoCTF{trust_but_verify_2cdcb2de}
  ```

---
