# Understanding the Linux File System

The Linux file system is organised in a hierarchical structure, starting from the root directory (*this is the top level of the file system where your user would live and any other users, and this contains personal directories for each user*).

The root directory is represented by a single forward slash: `/`. All other directories branch off from this root.

## Everything is a file in Linux

Unlike file systems you might be familiar with from Windows or Mac, Linux treats everything as a file.

This includes: 
- devices
- processes
- hardware components etc.

This structure provides a flexible and powerful way to manage your system. Understanding the Linux file system is essential, as it plays a crucial role in navigating and managing your files effectively.

# File & Directory Management: Essential Linux Commands

**Note:**  
A directory is the same as a folder. A file is content stored within a folder. These commands are fundamental for managing files and directories in Linux environments.


## Navigation and Directory Management

- `cd /`  
  Takes you to the root directory (the top-level folder).

- `cd`  
  Changes directory. For example, `cd "Desktop"` moves you into the Desktop folder.

- `cd ..`  
  Moves up one level in the directory structure (e.g., from `/home/desktop` to `/home`).

- `pwd`  
  Prints the working directory, showing your current location in the filesystem.

- `ls`  
  Lists the contents of the current directory.

- `ls -a`  
  Shows all files, including hidden files and directories (those beginning with `.` or `..`).

- `ls -L "directory"`  
  Displays the contents of the specified directory and all directories within it.

## Creating, Removing, and Managing Directories

- `mkdir "directory"`  
  Creates a new directory (folder).

- `mkdir -p "x/y/z"`  
  Creates nested directories in one command (e.g., creates `x`, then `y` inside `x`, then `z` inside `y`).

- `rmdir "directory"`  
  Removes an empty directory.

- `rm -r "directory"`  
  Removes a directory and all its contents (use with caution).

## File Creation, Viewing, and Deletion

- `touch "filename"`  
  Creates a new empty file.

- `rm "filename"`  
  Removes a file.

- `cat "filename"`  
  Displays the contents of a file.

- `head -n [number] "filename"`  
  Shows the first specified number of lines in a file.

- `tail -n [number] "filename"`  
  Shows the last specified number of lines in a file.

- `head -n [number] "filename" | tail -n [number]`  
  Shows the last specified number of lines from the first specified number of lines.

## File and Directory Operations

- `mv "source" "destination"`  
  Moves files or directories, or renames them.

- `cp "source" "destination"`  
  Copies files from the current directory to another location.

- `cp -r "source" "destination"`  
  Recursively copies directories and their contents.

## Searching and Information

- `locate "filename"`  
  Searches for a file (similar to search on Windows).

- `man "command"`  
  Opens the manual page for a command.

- `file ./*`  
  Lists the file types of all files in the current directory.

- `file */{.,}*`  
  Prints all files in all directories.

## Editing and Appending Content

- `echo "x" > "filename"`  
  Adds content to a file (overwrites existing content).

- `echo "y" >> "filename"`  
  Adds content to a file (does not remove existing content).

## Searching Within Files

- `grep "x" "filename"`  
  Searches for specific patterns/content (`x` in this case) within a file.

- `grep -v "xyz" "filename"`  
  Displays all lines in the file that **do not contain** the word "xyz".

## Permissions and Superuser Operations

- `sudo "command"`  
  Runs a command with superuser privileges (bypassing 'permission denied' errors).

- `sudo su`  
  Switches to the superuser account for continuous elevated access.

- `sudo !!`  
  Repeats the previous command with superuser privileges.

## Useful Keyboard Shortcuts

- `Ctrl + L`  
  Clears the terminal screen.

- `Ctrl + C`  
  Exits out of a running command.

- `!!`  
  Repeats the previous command.

