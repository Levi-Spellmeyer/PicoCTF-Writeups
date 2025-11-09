# PicoCTF - Obedient Cat

### <strong> 1.  Initial Info: </strong>

**Tags:** (Easy), (General Skills), (PicoCTF 2021)

**Author:** SYREAL

**Description:** This file has a flag in plain sight (aka "in-the-clear"). 

<img width="1002" height="629" alt="image" src="https://github.com/user-attachments/assets/e16c58ba-c4c8-4d7f-9685-ca3d8fac0e1e" />


<br>

## <strong>2. Initial Thoughts</strong>

- After opening up the attached web terminal the first command I ran was 
`ls -la`  to check out what files existed in the terminal.

<img width="706" height="251" alt="image" src="https://github.com/user-attachments/assets/f69e6d85-8a5c-4949-a224-7fba33c79f67" />



- The only file currently accessible was a README.txt and to view the contents of the file, I ran the following command:
`cat README.txt`

<img width="683" height="471" alt="image" src="https://github.com/user-attachments/assets/f283f765-5ba2-4dd1-835b-3e5748df768f" />


- The README file contained a general welcome message followed by tips and advice on using the web terminal to solve challenges including a brief introduction to navigating a cli using Linux commands

<img width="706" height="425" alt="image" src="https://github.com/user-attachments/assets/6aa750a0-6226-4d70-bed1-0952a7463633" />


- Despite the description of the challenge heavily implying that the flag is within the downloadable file, I still found it worth my time to familiarize myself with the terminal as it would have been important to be familiar with existing directories if they were present within web terminal.

<br>

## <strong>3. Getting to the flag</strong>

- To obtain the flag you must download the file containing the flag using the URL provided in the challenge description.

- In the web terminal type `wget` followed by the url to download the file. You can confirm the file successfully downloaded by typing `ls` and making sure it shows up in your current directory.

<img width="695" height="328" alt="image" src="https://github.com/user-attachments/assets/319c457a-c237-4fa0-8b46-c9799a93b96d" />


<img width="398" height="91" alt="image" src="https://github.com/user-attachments/assets/370d7c26-0e82-4535-95f2-97ad6c148001" />



- using the command `cat flag.txt` will show the contents of the flag file and reveal the flag to complete the challenge

<img width="349" height="66" alt="image" src="https://github.com/user-attachments/assets/c987166e-e0b5-41b0-b162-1260a0ce998b" />


<br>

## <strong>Provided Hints:<strong>
1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.

2. To get the file accessible in your shell, enter the following in the Terminal prompt:  `$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag`

4. `$ man cat`

<br>

## <strong>Takeaways and final notes<strong>

1. When using commands you are not familiar with, to see that commands manual page use `man`.
- When you type man into the terminal followed by a keyword/command, you will be shown all tags and flags you can append to the command/keyword to receive different kinds of outputs

<img width="698" height="793" alt="image" src="https://github.com/user-attachments/assets/148439e2-0257-4fd5-aeab-0b9752c85558" />


- Overall, this challenge serves as a simple onboarding exercise to familiarize users with the environment they will be working in while they take on other challenges.

<br>

## <strong>For more information:</strong>

For more information regarding topics and concepts covered in this lab you can check out the folowing links:

1. Linux Command manual page:
   - https://www.man7.org/linux/man-pages/man1/man.1.html

