# PicoCTF - Mod 26
---
### **Initial Info:**
**Tags:**              (Easy) (Cryptography) (picoCTF 2021)

**Author:**          PANDU

**Description:**   Cryptography can be easy, do you know what ROT13 is? values.txt

---
<img width="1042" height="516" alt="image" src="https://github.com/user-attachments/assets/2eadf047-51bc-48f1-adc8-3858f7a0075d" />


---
### **Initial Thoughts**

#### 1. Cryptography and Rot13
- Upon reading the description of the challenge, 2 things should stand out as important, the terms cryptography and ROT13. Cryptography is the practice and study of securing communications through the use of complex mathematical algorithms and keys. A key in cryptography is used as alongside a message or data input to encrypt or decrypt information. 
<br>

- ROT13 is classified as a substitution cipher that replaces each letter in a string with the letter 13 places after it in the alphabet. The 'ROT' in ROT13 is sometimes referred to as "Rotate" or "Rotate by." ROT13 is not intended to be used as a modern encryption algorithm as simply applying the algorithm to the encrypted text reveals the original text or plaintext.
<br>

- The algorithm to shift each letter in a string: final_position = (origional_position + 13) mod 26

#### 2. Cyberchef.org


<img width="1049" height="425" alt="image" src="https://github.com/user-attachments/assets/4ba2aa3c-3c0d-4ef7-9594-ba6595c8a977" />




___
### Getting to the Flag

Now that we know what ROT13 is and how to use Cyberchef, we can now tackle the challenge and get the flag. In the webshell provided by picoCTF the first command we want to use is the `wget` command followed by the link you get from right clicking `values.txt` and clicking copy. Without going into much detail just know that the `wget` command is used to download files from the internet using a URL.

--- 
<img width="1047" height="407" alt="image" src="https://github.com/user-attachments/assets/ae300646-fb26-49f7-929b-811e2dab3a91" />


--- 
We can see that a file values.txt was successfully downloaded and to view the contents of this file we will use `cat values.txt`.
___
<img width="718" height="97" alt="image" src="https://github.com/user-attachments/assets/fe813283-de5c-41c4-94b0-fcd00439843b" />


---
Navigating back to cyber chef we know that the string has been encrypted with rot13. So by searching up rot13 and dragging the appropriate block to the Recipe section, the output will display the decrypted message/flag.

---
<img width="1044" height="532" alt="image" src="https://github.com/user-attachments/assets/fe0a2ad7-d387-4912-ba35-fab26303a03c" />


---
put flag here
picoCTF{next_time_I'll_try_2_rounds_of_rot13_45559abd}

---
### Provided Hints:
1. This can be solved online if you don't want to do it by hand!

---
### Takeaways and Final Notes:
- mention cyberchef having a ton of different options
- talk about how ROT13 is not secure by modern standards but is an example of what cryptography is
- if you are unsure about what a command does use the manual page throught `man {command to learn more about}`


---
### For More Information:
1. Link to Cyberchef web tool --> [CyberChef](https://cyberchef.org/)
2. To read more about cryptography and why its important --> [What Is Cryptography? | IBM](https://www.ibm.com/think/topics/cryptography)
3. To learn more about ROT13 --> [ROT13 - Wikipedia](https://en.wikipedia.org/wiki/ROT13)
4. Linux Commands: man --> https://linuxconfig.org/learnin
5. To learn more about the `cat` and `wget` commands try using `man cat` and `man wget`
