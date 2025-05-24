# Introduction to the Terminal

The **terminal** is a command-line interface (CLI) that allows you to interact with your operating system by typing commands. It's a powerful tool used to:

- Navigate the file system  
- Run scripts  
- Install and configure software  
- Perform various administrative tasks  

When you type a command, is interpreted by the **shell** and gives back the output. We will cover the shell in more detail later, but for now, just know that it's what processes your commands.

# Introduction to the Shell

Linux commands are instructions we type into the terminal to communicate with the operating system through the **shell**.  
The shell is a user interface that connects users with the OS.
- The shell acts as a translator or middleman that takes our commands and makes the computer execute them.

![image](https://github.com/user-attachments/assets/af5dddd6-946b-41c9-93ba-77e0231adea7)


There are many types of shells, but the most common is **BASH** (Bourne-Again SHell).  
Each shell has different features but serves the same purpose.

![image](https://github.com/user-attachments/assets/19218ecf-4bbb-4eaa-932b-12a784d1b15a)


The shell is essential for scripting and running commands.

**To find out what shell you are using input the command:**  
```bash
echo $SHELL

```
## Binaries 
Commands like ``` echo ``` and ``` ls ``` are small programs written in a programming language and compiled into a format the computer can run execute.
- This compiled format is called a **binary.**

Programs are created by developers to perform specific tasks (e.g. ```ls``` lists directory contents).

When we type a command into the terminal, the shell:
- Reads the command and understands what we want and what to do.
- Searches for the program in directories specified by the **PATH environment variable.**
- Runs the binary program when found, executing the command.


## Understanding the PATH Environment Variable

The PATH variable lists directories where executable programs (binaries) are stored, usually ending in bin (short for binary).
- When we run a command like ``` ls ```, the shell searches these directories to find and run the appropriate program (binary).

  To list these directories enter the command: **echo $PATH**
- Each directory in PATH is separated by a colon (`:`) on Linux and macOS systems.

