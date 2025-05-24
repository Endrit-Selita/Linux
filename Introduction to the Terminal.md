# Introduction to the Terminal

The **terminal** is a command-line interface (CLI) that allows you to interact with your operating system by typing commands. It's a powerful tool used to:

- Navigate the file system  
- Run scripts  
- Install and configure software  
- Perform various administrative tasks  

When you type a command, the **shell** interprets it and returns the output. We'll cover the shell in more detail later, but for now, just know that it's what processes your commands.

---

## Key Things to Know

- Linux commands are ** textual instructions** entered directly into the terminal  
- They are **case-sensitive** (`ls` is not the same as `LS`)  
- Many commands support **options** (also called flags) and **arguments**  
- Most commands have a **manual page**, accessible via `man <command>`

---

## Anatomy of a Command

A typical command has three parts:

1. **The command itself** – e.g. `ls`  
2. **Options** – e.g. `-l` for long listing  
3. **Arguments** – e.g. a file or directory name  

**Example:**
```bash
ls -l /home/user
