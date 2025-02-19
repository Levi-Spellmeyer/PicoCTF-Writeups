# Summary

## **Challenge Overview**  
The challenge involved connecting to a remote instance via SSH and identifying an encrypted file containing the flag. A checksum was provided as a clue, and a decryption script was available to extract the flag once the correct file was found.

## **Key Steps and Challenges**  

### **1. Initial Exploration**  
- Connected to the instance using SSH.  
- Listed available files:  
  - A `checksum.txt` file containing a SHA-256 hash.  
  - A `decrypt.sh` script.  
  - A directory (`files/`) containing multiple text files with encrypted strings.  

### **2. Understanding the Decryption Process**  
- Reviewed `decrypt.sh`, identifying AES-256 encryption but determining it was unnecessary to manually decrypt files.  
- Recognized that the provided checksum likely corresponded to the SHA-256 hash of one of the files.  

### **3. Finding the Correct File**  
- Initially attempted grepping the provided checksum directly within the `files/` directory but got no matches.  
- Realized that SHA-256 checksums could be generated for all files using:  

  `sha256sum files/* `

### 4. Decrypting and Obtaining the Flag
- Ran ` ./decrypt.sh <identified_file> to decrypt the file. `
- Successfully retrieved the flag: ``picoCTF{trust_but_verify_2cdcb2de}.``
## Key Takeaways
- Checksums are useful for verifying file integrity and identification.
- Generating and comparing hashes can help locate specific files when a checksum is provided.
- Proper piping and command structuring are crucial for effective terminal operations.
- Understanding basic encryption and hashing concepts helped streamline the process.
