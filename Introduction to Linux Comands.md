# Linux commands

- Linux commands are **textual instructions** entered directly into the terminal, that tell the operating system what to do
- They are **case-sensitive** (`ls` is not the same as `LS`)  
- Many commands support **options** (also called flags) and **arguments**  
- Most commands have a **manual page**, accessible via `man <command>`

---

## Anatomy of a Command

A typical command has three parts:

1. **The command itself** – e.g. `ls`  
2. **Options** – e.g. `-l` for long listing  
3. **Arguments** – e.g. a file or directory name

![image](https://github.com/user-attachments/assets/70ac6a5f-7b15-4e16-9e1d-b0e917bd9d1d)


**Example:**
```bash
ls -a.

# This means: list (ls) all files – including hidden ones (-a) – in the current directory (.).
