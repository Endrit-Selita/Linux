# Environment Variables









# Environment Variables – Using and Modifying Shell Variables

## What Are Environment Variables?

- Environment variables are key-value pairs that store important system information and settings, such as your home directory (`HOME`), username (`USER`), shell (`SHELL`), and where to find programs (`PATH`).
- They affect how processes and commands behave on your system, and are essential for customising your Linux environment and streamlining your workflow.

<img src="https://github.com/user-attachments/assets/2db4cf31-91fc-48c4-87bc-23803fe1c993" width="450" />


- Common examples include:
  - `PATH` – Directories the system searches for executable files.
  - `HOME` – Your home directory.
  - `USER` – Your username.
  - `SHELL` – The shell you are using (e.g., bash, zsh).


<img src="https://github.com/user-attachments/assets/8ce4b166-1918-4ec2-9f69-c3f588efde6b" width="450" />

---

## Viewing Environment Variables

- **List all environment variables:**  
  `printenv`  
  or  
  `env`

- **View a specific variable:**  
  `echo $VARIABLE_NAME`  
  Example: `echo $HOME`

---

## Setting Environment Variables

### Temporary (Current Session Only)

- **Set a variable:**  
  `export MYVAR="hello world"`
- **Check it:**  
  `echo $MYVAR`
- This variable will only exist until you close the terminal.

### Permanent (Every Session)

- Add the export command to your shell’s configuration file:
  - For ZSH: `~/.zshrc`
  - For Bash: `~/.bashrc`
- Example: `export MYVAR="hello world`

- After saving, apply changes with:  
`source ~/.zshrc`  
or  
`source ~/.bashrc`
- Now the variable will be set every time you open a new terminal.

---

## Modifying Existing Variables

- **Add a directory to your PATH:**  

`export PATH="$PATH:/home/ubuntu/my_scripts"`

- This keeps existing directories and adds your new one at the end.

---

## Using Environment Variables in Scripts

- You can use environment variables in scripts to make them flexible and dynamic.  
Example script (`greet.sh`):

`#!/bin/bash
echo "Hello, $USER! 
Welcome to $HOSTNAME."`

- Make the script executable:  
`sudo chmod +x greet.sh`
- Run the script:  
`./greet.sh`

---

## How to Use Environment Variables in Practice

- To make a variable available in every session, add it to your shell config file (`.zshrc` or `.bashrc`).
- To use a variable just for now, use `export` in your current terminal.
- To see if your variable is set, use `echo $VARNAME`.
- To update a variable like `PATH`, always include the existing value (`$PATH`) so you don’t overwrite it.

---

## Why Is This Useful?

- Environment variables let you customise your Linux experience, automate tasks, and control how programs run.
- They are essential for scripting, programming, and system administration—skills that are highly valued by recruiters and employers.
- Mastering environment variables helps you manage user preferences, system paths, and configuration settings efficiently.

---

**Summary:**  
Environment variables are simple but powerful tools for storing settings and information in Linux. You can view, set, and make them permanent, and use them to make your scripts and system more flexible and efficient.
