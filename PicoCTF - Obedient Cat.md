# PicoCTF - Obedient Cat

### <strong> 1.  Initial Info: </strong>

**Tags:** (Easy), (General Skills), (PicoCTF 2021)

**Author:** SYREAL

**Description:** This file has a flag in plain sight (aka "in-the-clear").  


<img width="706" height="400" alt="image" src="https://github.com/user-attachments/assets/e16c58ba-c4c8-4d7f-9685-ca3d8fac0e1e" />


<br>

---

- After opening up the attached web terminal which can be found on the right side of the screen,  the first command I ran was  `ls -la`  to see what directories or files already exist.
- Think of a directory as a folder that can contain other folders or files
- The `ls -la` command lists all files in your current directory and combine the outputs of `-l` and `-a` flags
- Appending the `-l` flag to the end of your `ls` command specifies that you want to list the files in your current directory in a 'long' format, displaying file type, permissions, as well as other information
- Appending the `-a` to the `ls` command specifies that you want to list all files including hidden files (files that start with ' . ')

---
  
<img width="706" height="251" alt="image" src="https://github.com/user-attachments/assets/f69e6d85-8a5c-4949-a224-7fba33c79f67" />

---

- The only file that stands out after running the `ls -la` command is README.txt
- If you look at the listed files and folders, the only one that instantly stands out is the .txt file
- To view the contents of the file, I ran the following command: `cat README.txt`
- The `cat` command followed by a file name will output that files contents to your terminal
- In the case of the README.txt the following was displayed

---

<img width="683" height="471" alt="image" src="https://github.com/user-attachments/assets/f283f765-5ba2-4dd1-835b-3e5748df768f" />

---

- The README file contains a general welcome message followed by tips and advice on using the web terminal to solve challenges including a brief introduction to navigating a cli using Linux commands

---

<img width="706" height="425" alt="image" src="https://github.com/user-attachments/assets/6aa750a0-6226-4d70-bed1-0952a7463633" />

---

- Despite the description of the challenge heavily implying that the flag is within the downloadable file provided, I still found it worth my time to familiarize myself with the terminal as it would have been important to be familiar with existing directories if they were present within the web terminal.

---

<br>

## <strong>3. Getting to the flag</strong>
- To obtain the flag you must download the provided file containing the flag using the URL found in the challenge description.
- Right click the blue 'Download flag' text and copy the link
- In the web terminal type `wget` then right click and click paste, then enter
-  The `wget` command downloads a file using a specified URL typically following format: `wget URL-HERE`. This command will be used across numerous challenges and is worth remembering. 
- After running the above `wget` command, you can confirm the file successfully downloaded by typing `ls` or `ls -la` to check if it shows up in your current directory.

---

<img width="695" height="328" alt="image" src="https://github.com/user-attachments/assets/319c457a-c237-4fa0-8b46-c9799a93b96d" />


<img width="398" height="91" alt="image" src="https://github.com/user-attachments/assets/370d7c26-0e82-4535-95f2-97ad6c148001" />

---

-  using the cat command once more, `cat flag.txt` will show the contents of the flag file and reveal the flag needed to complete the challenge

---

<img width="349" height="66" alt="image" src="https://github.com/user-attachments/assets/c987166e-e0b5-41b0-b162-1260a0ce998b" />

---

<details>
<summary>Click Here to Reveal the Flag</summary>


	picoCTF{s4n1ty_v3r1f13d_4a2b35fd}

</details>
<br>

---

## <strong>Provided Hints:</strong>

1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.

2. To get the file accessible in your shell, enter the following in the Terminal prompt:  `$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag`

3. `$ man cat`

<br>

## <strong>Takeaways and final notes</strong>

- When using commands you are not familiar with, to see that commands manual page use `man`.
- When you type man into the terminal followed by a keyword/command, you will be shown all tags and flags you can append to the command/keyword to receive different kinds of outputs

<img width="698" height="793" alt="image" src="https://github.com/user-attachments/assets/148439e2-0257-4fd5-aeab-0b9752c85558" />


- Overall, this challenge serves as a simple onboarding exercise to familiarize users with the environment they will be working in while they take on other challenges.
<br>

---

> [!TIP]
> For more information regarding topics and concepts covered in this lab you can check out the folowing links:
> 1. Linux Command manual page:  https://www.man7.org/linux/man-pages/man1/man.1.html

---
