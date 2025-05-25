

# File Permissions

## What Are File Permissions?

- File permissions control who can read, write, or run (execute) a file or folder.
- There are three types of permissions:
  - **Read (r):** View the contents.
  - **Write (w):** Change or delete the contents.
  - **Execute (x):** Run the file as a program or script.

- Permissions are set for three groups:
  - **User (owner):** The person who owns the file.
  - **Group:** Other users in the same group.
  - **Other:** Everyone else on the system.

- You can see permissions using `ls -l`. For example: `-rwxr--r--`  
  - The first character shows if it’s a file (-) or directory (d).
  - The next three are for the user, then group, then others.
 
<img src="https://github.com/user-attachments/assets/2c23d906-f023-48b4-945d-dce296dfc584" width="450" />

---

## How Are Permissions Written?

- **String format:** `rwxrwxrwx` (user, group, other).
- **Octal (numeric) format:** Each permission is a number:
  - Read = 4, Write = 2, Execute = 1.
  - Add them up for each group, e.g. `rwx` = 7, `rw-` = 6, `r--` = 4, so `chmod 764 filename`[1].
- **Binary format:** Each permission is represented by 1 (granted) or 0 (not granted)
  - rwx = 111, rw- = 110, r-- = 100
 
<img src="https://github.com/user-attachments/assets/44ecf741-7c86-43fb-950b-4266c987daad" width="500" style="border: 40px solid black;" />

You can practice calculating permissions using this handy online tool: [CHMOD Calculator](https://chmod-calc-five.vercel.app/)

---

## Changing Permissions: The `chmod` Command

- Use `chmod` to change permissions:
  - **Symbolic:** `chmod u+x,g+r,o-w filename`  
    (user gets execute, group gets read, others lose write)
  - **Numeric:** `chmod 744 filename`  
    (user: all, group: read, others: read)
  - To give all users execute: `chmod +x filename`
  - To set specific permissions: `chmod ug=rw,o=r filename`.

---

## Changing File and Directory Ownership

- **Owner and group** are shown in `ls -l` (the 2nd column is the user owner (🔴 red), and the 3rd is the group owner (🔵 blue)).

<img src="https://github.com/user-attachments/assets/e82189df-0b0d-49e2-a49e-2cb23d312781" width="400" />

- **Change owner:**  
  `sudo chown new-owner filename`  
  This command changes the owner of a single file (or directory), but not the contents inside a directory. 

- **Change group:**  
  `sudo chgrp new-group filename`

For example, if you want to change the ownership of `example.txt` so the **user** is `username` and the **group** is `europe`:
- `sudo chown username example.txt`
- `sudo chgrp europe example.txt`

<img src="https://github.com/user-attachments/assets/2f8a8382-db6c-45d4-937d-bec964ea11b1" width="400" />

If you check with `whoami`, you might see you are logged in as `ubuntu`. In this example, the user is `username` and the group is `europe`, so you are considered "other". The permissions for `example.txt` are read-only for you (as shown by `--r`).

If you try to edit the file with `vim example.txt`, you will see it is read-only unless you use `sudo` to elevate your permissions.

<img src="https://github.com/user-attachments/assets/3bd6800c-079b-41ac-ba9d-9cbd6dd88ab9" width="400" />

- If you are the root user, you can bypass restrictions with `sudo`, which gives you superuser access.

- **Change both user and group at once:**  
  `sudo chown new-owner:new-group filename`

- **To change a directory (and all its contents):**  
  `sudo chown -R new-owner:new-group directory-name`  

  The `-R` option makes the change recursive, so it affects the directory and everything inside it—including all files and subdirectories, even hidden ones.  

  Otherwise, you will only be the owner of the directory itself, not of the files and subdirectories within it. This is crucial for keeping ownership consistent and avoiding permission issues, especially when transferring or managing large folders or projects[4][7].

---

## Why Does This Matter?

- Correct permissions and ownership keep your files safe and private.
- Only the right people can read, edit, or run your files.
- Essential for security and good system management—skills every IT professional needs.

---

**Summary:**  
File permissions in Linux decide who can see, change, or run files and folders. You manage them using `chmod` for permissions and `chown`/`chgrp` for ownership. Understanding this keeps your system secure and organised, and shows you know your way around Linux.


