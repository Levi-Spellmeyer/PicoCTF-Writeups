# PicoCTF - What's a net cat?

---

<strong>1. Initial Info:</strong>

**Tags:**  (Easy) (General Skills) (picoCTF 2019)
**Author:** SANJAY C/DANNY TUNITIS
**Description:** Using netcat (nc) is going to be pretty important. Can you connect to fickle-tempest.picoctf.net at port {port number} to get the flag
___ 
![[Pasted image 20251202094107.png]]

---
>[!Note]
>- One quick note for this challenge is that the description only appears after launching the instance. Do not worry if you open the initial challenge page and their are no instructions.

---
<strong>Initial Thodughts and Information</strong>
- Upon reading the description of the challenge, take note of the emphasized netcat command denoted (nc). Even without knowing what the command or tool is, we can assume the nc is the syntax for what we will be using in this challenge
- The description of the challenge lists a port number so we should remember to look for any specific flags or syntax that allows us to specify what port we would like to use the netcat command on.


---

**So What is a net cat?** 
According to LinuxVox.com (link provided below), Netcat is a light weight tool that can establish TCP and UDP connections to transfer data bidirectionally. LinuxVox lists the following as other key features of Netcat:
1. Port scanning
2. File/stream transfer
3. command execution
4. Listening mode (acts as a server accepting incoming traffic)
5. Client mode (Connect to remote servers on specific ports)

---

So before even checking the man page for the Netcat tool, we now know that more than likely we will in some way either be listening for an outside connection or be connecting to a remote server using the port provided to us in the challenge

---

<strong>Getting to the flag</strong>
After reading a bit about the Netcat tool and launching the instance, the first command I ran was ls -la. While I do not expect to find any challenge related files, I find it a good habit when approaching a new challenge to establish a baseline of what exists in the terminal or system before continuing on with the challenge. 
<details>
<summary>More about `ls -la`</summary>
Appending the `-l` flag to the end of your `ls` command specifies that you want to list the files in your current directory in a 'long' format, displaying file type, permissions, as well as other information Appending the `-a` to the `ls` command specifies that you want to list all files including hidden files (files that start with ' . ')

</details>
---
![[Pasted image 20251202094346.png]]
---
Since there are no notable files within the web terminal I decided to move forward with what I saw as the next logical step for this challenge and that is to check the manual page for netcat. Since I am almost positive that this challenge revolves around the tool, finding out the appropriate syntax is important.

The command to open the manual page for netcat is `man nc`

---
>[!note]
>we are given a web address and a port so we may need to also look for a flag to specify port in the manual page

---
![[Pasted image 20251202094414.png]]

---
So within this manual page we can see confirmation that this utility does allow for port scanning, listening for traffic on specified ports, and for outbound connection.

Looking through the synopsis at the top of the page the first thing that caught my eyes was the source port flag `-p` if you scroll down this manual page you will also see the -p flag again with a bit more of a description behind its functionality.

---

 <img>20251202094533.png</img>


---
In my haste to solve the challenge I failed to read the description for the -p flag and failed to realize it was not the correct way to specify a port when trying to make a connection to an outside client/server.

When I tried to run the command it displayed and error and upon looking back in the manual page, at the end of the synopsis you can see it says '[port]'. 

Looking one set of brackets before the port specification you can see square brackets with the word destination in it. This made it clear to me that the syntax I was looking for was `nc [destination] [port]`.

Trying this string filled in with the provided information from the challenge description revealed to me the flag.

![[Pasted image 20251202094940.png]]

<strong>Provided Hints</strong>
1. 



<strong>Takeaways and final notes</strong>
1. This challenge was a good introduction to the Netcat tool and just like previous challenges, seemed to be a simple introduction to the tool to stress its importance in future challenges.
2. When reading manual pages for different commands , you will notice that many will share the same flag formats but do not always use them to complete the same functionality. In this challenge I assumed that a -p flag would be used to specify the port I wanted to make a connection to and that was shown to not be the case. 


<strong>For more information</strong>
1. https://linuxvox.com/blog/netcat-nc-command-with-examples/
2. 
