# Users & Groups

## What Are Users and Groups?

- **Users** are individual accounts on a Linux system. Each user can have their own files and settings.
- **Groups** let you organise users and manage permissions easily. A user can be in more than one group.

---

## User Management

- **Create a new user:**  
  `sudo useradd "username"`
- **Set a password for a user:**  
  `sudo passwd "username"`
- **Switch to another user:**  
  `su - "username"`
- **Check your current user:**  
  `whoami`
- **Exit back to your previous user:**  
  `exit`

### Giving and Removing Admin (sudo) Rights

- **Give a user admin rights:**  
  `sudo usermod -aG sudo "username"`
  - This adds the user to the `sudo` group, allowing them to run admin commands.
- **Remove admin rights:**  
  `sudo deluser "username" sudo`

  
- **Test if a user has sudo:**  
  Log in as that user and try a command like `sudo apt-get update`. If it fails, they don’t have admin rights.

---

## Group Management

- **See all groups:**  
  `cat /etc/group`
- **Create a new group:**  
  `sudo groupadd "groupname"`
- **Add a user to a group:**  
  `sudo usermod -aG "groupname" "username"`
- **Add a user to multiple groups:**  
  `sudo usermod -aG group1,group2 "username"`
- **Remove a user from a group:**  
  `sudo gpasswd -d "username" "groupname"`
- **See what groups you’re in:**  
  `groups`
- **Delete a group:**  
  `sudo groupdel "groupname"`
- **Find a specific group:**  
  `grep "groupname" /etc/group`

---

## Key Points

- When you give a user sudo rights, you’re adding them to the `sudo` group, which is like the admin group.
- Only users in the sudo group can run admin commands or access protected directories like `/root`.
- Users can belong to multiple groups for flexible permission management.
- Managing users and groups is essential for controlling who can do what on a Linux system.
