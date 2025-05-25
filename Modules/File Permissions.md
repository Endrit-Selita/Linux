

# File Permissions in Linux: Simple Notes

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

- **Owner and group** are shown in `ls -l` (2nd column represents the user owner (🔴 red), the 3rd is the group owner (🔵 blue)).


<img src="https://github.com/user-attachments/assets/e82189df-0b0d-49e2-a49e-2cb23d312781" width="400" />
  
- Change owner **files only**:  
  `sudo chown new-owner filename`
- Change group:  
  `sudo chgrp new-group filename`

On the image let's change the ownership of`example.txt`. if we want to change the **user** to `username` and the **group** to `europe`
- `sudo chown username example.txt`
- `sudo chgrp europe example.txt`

<img src="https://github.com/user-attachments/assets/2f8a8382-db6c-45d4-937d-bec964ea11b1" width="400" />

With the command `whoami` - I can see i am ubuntu. The user is username, the group is europe, so i am considered other. My file permissions for example.txt is read only as you can see it is --r.

To search this, i typed in the command `vim example.txt` and it states it is read only

<img src="https://github.com/user-attachments/assets/3bd6800c-079b-41ac-ba9d-9cbd6dd88ab9" width="400" />

  - If you are the root user you can bypass with sudo which elevates permission to root user

- Change both user and group at once:  
  `sudo chown new-owner:new-group filename`
- Change **directories** ownership and contents:  
  `sudo chown -R new-owner:new-group directory-name`[1].

---

## Why Does This Matter?

- Correct permissions and ownership keep your files safe and private.
- Only the right people can read, edit, or run your files.
- Essential for security and good system management—skills every IT professional needs[1][2][3].

---

**Summary:**  
File permissions in Linux decide who can see, change, or run files and folders. You manage them using `chmod` for permissions and `chown`/`chgrp` for ownership. Understanding this keeps your system secure and organised, and shows you know your way around Linux.


