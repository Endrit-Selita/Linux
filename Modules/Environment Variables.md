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
- Example:
