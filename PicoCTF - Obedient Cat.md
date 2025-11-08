# PicoCTF - Obedient Cat

### <strong> 1.  Initial Info: </strong>

**Tags:** (Easy), (General Skills), (PicoCTF 2021)

**Author:** SYREAL

**Description:** This file has a flag in plain sight (aka "in-the-clear"). 


Note Insert picture here of the challenge menu

<br>

## <strong>2. Initial Thoughts</strong>

After opening up the attached web shell the first command I ran was 
`ls -la`  to check out what files existed in the shell.

note insert picture of the ls -la and the cated readme


The only file currently accessible was a README.txt and to view the contents of the file, I ran the following command:
`cat README.txt`

Screenshot readme

The README file contained a general welcome message followed my tips and advice on using the web shell to solve challenges including a brief introduction to navigating a cli using Linux commands

screenshot of readme linux portion

Despite the description of the challenge heavily implying that the flag is within the downloadable file, I still found it worth my time to familiarize myself with the shell as it would have been important to be familiar with existing directories if they existed on the shell.

<br>

## <strong>3. Getting to the flag</strong>

To obtain the flag you must download the file containing the flag using the URL provided in the challenge description.

In the web shell type `wget` followed by the url to download the file. You can confirm the file successfully downloaded by typing `ls` and making sure it shows up in your current directory.

picture of wget download

picture of the ls containing the flag


using the command `cat flag.txt` will show the contents of the flag file and reveal the flag to complete the challenge

note show flag with marked out inside part only showing the picoCTF{ }

<br>

## <strong>Provided Hints:<strong>
1. Any hints about entering a command into the Terminal (such as the next one), will start with a '$'... everything after the dollar sign will be typed (or copy and pasted) into your Terminal.

2. To get the file accessible in your shell, enter the following in the Terminal prompt:  `$ wget https://mercury.picoctf.net/static/a5683698ac318b47bd060cb786859f23/flag`

4. `$ man cat`

<br>

## <strong>Takeaways and final notes<strong>

1. When using commands you are not familiar with. A helpful linux command is `man`.
- When you type man into the terminal followed by a command, you will be shown all tags and flags you can attach to the command to receive different outputs.

picture of the man cat page

Overall, this challenge serves as a simple onboarding exercise to familiarize users with the environment they will be working in while they take on other challenges.

<br>

## <strong>For more information:</strong>
