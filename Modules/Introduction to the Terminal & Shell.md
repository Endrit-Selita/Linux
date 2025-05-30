# Introduction to the Terminal

The **terminal** is a command-line interface (CLI) that allows you to interact with your operating system by typing commands. It's a powerful tool used to:
- Navigate the file system  
- Run scripts  
- Install and configure software  
- Perform various administrative tasks

When you type a command, is interpreted by the **shell** and gives back the output. We will cover the shell in more detail later, but for now, just know that it's what processes your commands.

&nbsp;

# Introduction to the Shell

The shell is essential for scripting and running commands.

Linux commands are instructions we type into the terminal to communicate with the operating system through the **shell**. 
The shell is a user interface that connects users with the OS.
- The shell acts as a translator or middleman that takes our commands and makes the computer execute them.

&nbsp;

![image](https://github.com/user-attachments/assets/af5dddd6-946b-41c9-93ba-77e0231adea7)

&nbsp;

There are many types of shells, but the most common is **BASH** (Bourne-Again SHell).  
Each shell has different features but serves the same purpose:
- Zsh: Highly customizable with improved auto-completion and spell correction.
- Fish: Provides intuitive syntax highlighting and suggestions out of the box.

Choose a shell based on your personal preference and needs.

&nbsp;

![image](https://github.com/user-attachments/assets/19218ecf-4bbb-4eaa-932b-12a784d1b15a)

&nbsp;

**To find out what shell you are using input the command:**  
```bash
echo $SHELL
```

**Checking Available Shells on your system :**  
```bash
cat /etc/shells
# the command cat looks into the contents of the file
```

&nbsp;

## Installing a new Shell - ZSH

ZSH is one of the most popular alternative shells for Linux. It offers advanced features such as:

- Powerful auto-completion  
- Spelling correction  
- Extensive customisation options  

Many developers and DevOps engineers prefer ZSH because it allows for a more personalized and efficient command-line experience.

&nbsp;

### If ZSH is not already installed on your system, follow these steps:

1. Open your terminal.
2. Since this example uses an Ubuntu/Debian-based system, use the APT package manager to install ZSH:

   ```bash
   sudo apt-get install zsh
   ```
- If prompted with "Do you want to continue?", type ```Y``` and press Enter.

After installation, simply type: ```zsh```
This will switch your shell to ZSH. You'll notice the prompt and interface change, indicating you are now in the ZSH shell.

Switching Back to Bash
- To return to the Bash shell, just type: ```bash```. This will switch you back to your previous shell

&nbsp;

### Making ZSH deafult Shell

Even after installing ZSH, your terminal might still start with Bash by default. You can check your current default shell with `echo $SHELL`.

To make ZSH the dfault shell, use the `chsh -s /bin/zsh` command. This will prompt you to enter your password. To avoid this repeat the last command with elevated privileges `sudo chsh -s /bin/zsh`.
- the change won’t show up until you open a new terminal session

&nbsp;

If that did not work than another command you can use is `sudo chsh -s $(which zsh) $(whoami)`

What This Command Does:
- `chsh -s`: The command to change the shell.
- `$(which zsh)``#: This returns the full path of the ZSH binary (e.g. `/usr/bin/zsh`).
- `$(whoami)`: This returns the current username (e.g. ubuntu).

&nbsp;

### Customise your ZSH with OhMyZsh

OhMyZSH is a popular framework for managing your ZSH configuration with a wide range of plugins, themes, and features that enhances your ZSH experience.

Run the command `sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`
- a popular theme is powerlevel10k
- please see tutorials online on different custtomisations you can add once you run this command

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

