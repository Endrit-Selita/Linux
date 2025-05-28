# Data Redirection in Linux: Pipes, Output & Input Redirection

## What is Data Redirection?

Data redirection in Linux lets you control where input comes from and where output goes. Instead of always using the keyboard for input and the screen for output, you can send data between files, commands, or even discard it. This is a core skill for working efficiently with the command line.

---

## Standard Streams

Linux uses three standard streams:
- **Standard Input (STDIN, 0):** Where commands get their input (usually the keyboard).
- **Standard Output (STDOUT, 1):** Where commands send their output (usually the terminal screen).
- **Standard Error (STDERR, 2):** Where error messages are sent (also the terminal by default).

 &nbsp;

![image](https://github.com/user-attachments/assets/2342fad1-6c5e-439f-9447-5851d30b491d)

 &nbsp;

---

## Output Redirection

Output redirection lets you control where the output of a command goes, instead of always displaying it on the terminal screen. Here are some simple examples:

- **Redirect output to a file (overwrite):**  
  `echo "Hello, world!" > hello.txt`  
  This command writes "Hello, world!" to `hello.txt`. If the file exists, it will be overwritten.

- **Redirect output to a file (append):**  
  `echo "Another line" >> hello.txt`  
  This adds "Another line" to the end of `hello.txt` without deleting what’s already there.

- **Redirect the output of a command:**  
  `ls > files.txt`  
  Saves the list of files in the current directory to `files.txt` instead of printing them on the screen.

- **Redirect errors to a file:**  
  `ls /nonexistent 2> errors.txt`  
  Any error messages (like "No such file or directory") will be saved in `errors.txt`.

- **Redirect both output and errors to the same file:**  
  `ls /nonexistent > alloutput.txt 2>&1`  
  or  
  `ls /nonexistent &> alloutput.txt`  
  Both the normal output and error messages will be saved in `alloutput.txt`.

- **Discard output completely:**  
  `ls /nonexistent &> /dev/null`  
  This command sends both output and errors into the "black hole" (`/dev/null`), so nothing appears or is saved anywhere.

---

## Input Redirection

- **Read input from a file instead of the keyboard:**  
  `command < filename`  

   Example: `cat < file.txt` the command takes its input from the file, not from what you type.

### Difference between `cat file.txt` and `cat < file.txt`

Both `cat file.txt` and `cat < file.txt` will display the contents of `file.txt` on the terminal, but there is a subtle difference in how they work:

- **`cat file.txt`:**  

   The `cat` command is given the filename as an argument. `cat` itself opens the file, reads its contents, and prints them to the screen. You can also give multiple files as arguments (e.g., `cat file1.txt file2.txt`).

- **`cat < file.txt`:**  

  Here, the shell (not `cat`) opens the file and redirects its contents to the standard input (STDIN) of `cat`. `cat` receives no filename argument and simply reads whatever comes in through STDIN—in this case, the contents of `file.txt`].

**In practice, for `cat`, both commands give the same result for a simple file.**  
However, the difference is:
- With `cat file.txt`, `cat` opens the file itself.
- With `cat < file.txt`, the shell opens the file and feeds it to `cat` as input.

This distinction can matter for some commands or in special cases (such as when using `sudo` or handling files named with special characters), but for everyday use, both are fine for displaying a file's contents.

**Tip:**  
Input redirection (`<`) is especially useful for commands that expect to read from standard input, such as `tr`, `sort`, or `awk`, allowing you to feed them a file without needing to type or paste its contents.

---

## Pipes (|)

- **Send output from one command directly as input to another:**  
  `command1 | command2`  

   For example:  
  `ls | less`  
  Shows the output of `ls` one page at a time using `less`.

- **Chain multiple commands:**  
  You can use pipes to connect several commands together, processing data step by step:  
  `cat file.txt | grep "error" | sort | uniq > unique_errors.txt`  
  This finds lines with "error", sorts them, removes duplicates, and saves the result.

---

## Special Redirection: Discarding Output

- **Send unwanted output to /dev/null:**  
  `command > /dev/null`  
  Discards normal output.


- **Discard errors:**  
  `command 2> /dev/null`  
  Discards error messages.

- **Discard both:**  
  `command &> /dev/null`

  Example: `ls nonexistant desktop &> /dev/null` - This discards the error message for the non-existent directory and the output of `ls desktop`, so nothing is shown on the terminal.

 This command sends both output and errors into the "black hole" (`/dev/null`), so nothing appears or is saved anywhere. Useful for hiding all output when you don’t want to see it.

 
---

## Why Does This Matter?

- Redirection and pipes let you automate tasks, process data efficiently, and keep your terminal tidy.
- These skills are used daily in scripting, troubleshooting, and data processing — essential for any technical role
