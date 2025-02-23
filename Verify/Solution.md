# **CTF Writeup: Identifying and Decrypting an Encrypted File**

## **Challenge Overview**  
This challenge involves connecting to a remote instance via SSH, identifying an encrypted file containing the flag, and decrypting it using a provided script. A checksum is given as a clue to locate the correct file.

---

## **Step-by-Step Walkthrough**

### **Step 1: Connecting to the Remote Instance**
1. Use the provided SSH credentials to access the remote machine:
   ```bash
   ssh user@remote-server
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
