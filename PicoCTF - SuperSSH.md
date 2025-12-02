# PicoCTF - Super SSH


---
### <strong>Initial Info</strong>:
**Tags:** (Easy) (General skills) (picoCTF 2024) (shell) (SSH) (browser_webshell_solvable)

**Author:** JEFFERY JOHN

**Description:** Using a Secure Shell (SSH) is going to be pretty important. Additional details will be available after launching your challenge instance.

---

<img width="866" height="660" alt="image" src="https://github.com/user-attachments/assets/2a99d971-6105-47bd-9922-12947cf0003c" />

---
### <strong>Initial Thoughts</strong>

- After reading the description of the challenge I do not have to launch the instance or open the browser web shell to ask, what is a secure shell?

--- 

#### What is a Shell?
>[!Important]
The terms "CLI", "Terminal", and "CMD" are informally used to refer to a shell and are most commonly recognized. Going forward be sure to keep in mind that:
>- The terminal is the interface you see as you type in commands
>- The shell is the program used to interpret commands

The image below is off the terminal within the web shell provided by PicoCTF
<img width="857" height="307" alt="image" src="https://github.com/user-attachments/assets/cb1683a8-7a35-4d7d-b3b9-1f9b0dcb7e1b" />

---
### What a Secure Shell (SSH) actually does
 >[!Important]
> - Creates an encrypted connection between two computers
>- Authenticates the remote machine and the user looking to open a remote connection. 

---
### Think of it like this
- SSH  is like remote controlling another computer's command line from your own computer. All you have to do is sign in from your command line to ensure there is a secure and stable connection.

--- 
### Back to the challenge

- After reading up on SSH and starting the instance, I opened the web terminal and as I always do run the `ls -la` command to see what files and directories exist within the terminal.
<details>
<summary>More about `ls -la`</summary>
Appending the `-l` flag to the end of your `ls` command specifies that you want to list the files in your current directory in a 'long' format, displaying file type, permissions, as well as other information Appending the `-a` to the `ls` command specifies that you want to list all files including hidden files (files that start with ' . ')

</details>

___ 

<img width="853" height="348" alt="image" src="https://github.com/user-attachments/assets/2398a550-850a-460e-bba8-bc46df8e34a5" />

--- 
>[!Note]
>Note that in my previous writeup of the challenge "Obedient Cat" we downloaded the file "flag." This tells me that files are persistent across the different challenges and to verify this theory I copied the flag within the file and it did not complete the challenge.
> 
> You can find my writeup for the "Obedient Cat" challenge [here](https://github.com/Levi-Spellmeyer/PicoCTF-Writeups/blob/main/PicoCTF%20-%20Obedient%20Cat.md)


- After determining there was nothing within the terminal I would need I decided to look at the manual page for SSH and ran the command `man ssh`

--- 

<img width="855" height="492" alt="image" src="https://github.com/user-attachments/assets/224a61ab-372e-412b-8489-b49b288f36ae" />

---
### <strong>Getting to the flag</strong>
- Looking at the man page for ssh or the image above, you will see that the given format for the command is `ssh user@destination:port`

- I used this format plugging in the user, destination, and port (given in the challenges extended description once you launch the instance) and received the following error

<img width="869" height="131" alt="image" src="https://github.com/user-attachments/assets/1d923cfa-7789-42b6-9733-345ea378a8a9" />

--- 
- Confused as to why I got the error despite following the format within the manual page I tried running the command a few different times changing up the format a little bit each time, each time getting a permission denied or hostname resolution error
---
<img width="882" height="222" alt="image" src="https://github.com/user-attachments/assets/934e5834-98df-4775-a473-0b067024d578" />

---
- After failing a few more times I decided to recheck the manual page and after scrolling down, found the correct tag to let me specify the port to make a connection through
---

<img width="867" height="390" alt="image" src="https://github.com/user-attachments/assets/52885442-cc63-426a-966f-6b060064f310" />

___
- This time using the `-p` flag followed by the specified port I was able to create a connection and use the provided username and password to receive the flag to complete the challenge
---
<img width="873" height="211" alt="image" src="https://github.com/user-attachments/assets/80486d81-32fb-41b9-ae2b-bf35439e5bf3" />

---
<details>
<summary>Click Here to Reveal the Flag</summary>


	picoCTF{s3cur3_c0nn3ct10n_5d09a462}

</details>

--- 
### <strong>Provided Hints</strong>
1. https://linux.die.net/man/1/ssh
2. You can try logging in 'as' someone with `<user>`@titan.picoctf.net
3. How could you specify the port?
4. Remember, passwords are hidden when typed into the shell

---

### <strong>Takeaways and final notes</strong>

- **SSH (Secure Shell)** is a protocol that lets you securely access another machine’s command-line over an encrypted connection. You’ll use it often in CTFs to access remote environments, read files, and interact with running services.

- A **shell** is the command interpreter, while a **terminal** is the interface that displays it. This distinction is helpful when troubleshooting or working with different environments (browser shells, local terminals, SSH sessions, etc.).

- When you’re unsure about command usage, the **manual pages (`man ssh`) are incredibly helpful**. They provide correct syntax, flag descriptions, and examples.

- **Passwords won’t show up as you type them** during SSH login—this is normal and intentional

- Files inside PicoCTF’s web shell **are not shared across challenges**, so previously downloaded flags or artifacts won’t appear in new challenge instances

- This challenge required us to use the -p flag because we were attempting to SSH into the system on a non standard port. Be sure to review the manual pages for commands you are not familiar with as CTF challenges will often require you to use commands outside their standard forms.

--- 


