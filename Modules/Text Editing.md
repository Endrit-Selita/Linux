# Text Editing

To edit texts we use the command `vim`. Vim is a text editor, a tool for creating and editing plain text files. Unlike word processors, vim is designed for editing code, configuration files, scripts, and documentation directly from the terminal. It is renowned for its speed, efficiency, and powerful features, all accessible through keyboard commands without needing a mouse or menus.

## How to Open and Use Vim

To start editing a file with vim, use the following command in your terminal: `vim 'filename.txt'`
- If the file does not exist, Vim will create it for you.
- If the file exists, Vim will open it for editing.

## Key Modes in Vim

Vim features three main modes, each serving a distinct purpose:

- **Insert Mode**  
  Used for entering and editing text directly. Press `i` to enter Insert Mode, and `Esc` to return to Command Mode.

- **Visual Mode**  
  Allows you to select and manipulate blocks of text. Enter Visual Mode by pressing `v`.

- **Command Mode**  
  The default mode when you open Vim. Used for navigation, issuing commands, and performing edits. Press `Esc` at any time to ensure you are in Command Mode.

When you open Vim, it starts in **Command Mode** (also called Normal Mode)

## Essential Commands

### File Management

- `:w` — Save (write) changes to the current file.
- `:q!` — Quit without saving changes.
- `:wq!` — Save changes and force quit Vim.

### Navigation Shortcuts

- `0` — Move the cursor to the start of the current line.
- `$` — Move to the end of the current line.
- `w` — Move forward one word at a time.
- `b` — Move backward one word at a time.
- `:line_number` — Jump directly to a specific line (e.g., `:15` to go to line 15).
- `/word` — Search for a specific word or pattern in the file.
  - Press `n` to jump to the next match.
  - Press `N` to jump to the previous match.

### Editing Commands

- `dd` — Delete the entire current line.
- `D` — Delete from the cursor position to the end of the line.
- `yy` — Copy (yank) the current line.
- `p` — Paste the copied or deleted content after the current line.
- `u` — Undo the last change.
- `Ctrl + r` — Redo the previously undone change.

### Display & Customisation

- `:syntax on` — Enable syntax highlighting for improved readability.
- `:set number` — Show line numbers alongside your text.
- `:set nonumber` — Hide line numbers.



## Tips for New Vim Users

- **Switching Modes:**  
  Always press `Esc` if you are unsure which mode you are in; this will reliably return you to Command Mode.

- **Help System:**  
  Access Vim’s built-in help at any time by typing `:help` in Command Mode.
