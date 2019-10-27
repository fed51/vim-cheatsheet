# VIM Cheat Sheet

![I❤️ VIM](images/I_heart_vim.png)

## For New VIM Enthusiasts

This cheat sheet assumes that the reader alreading has a basic understanding of how to open, edit, save, and exit, VIM.

This guide is a work-in-progress and I will be adding to it over time.

## Table of Contents

1. [.vimrc Magic](#vimrc-magic)
1. [Buffers](#buffers)
   1. [Basics](#basics)
   1. [Delete Buffers](#delete-buffers)
   1. [Delete Other Buffers](#delete-other-buffers)

### .vimrc Magic

***Change Detection***

Check if file has been changed externally and reload into buffer:

`au FocusGained,BufEnter * :silent! checktime`

***Auto-Save***

Auto-save on window focus is lost:

`au FocusLost,WinLeave * :silent! w`

***Mouse Functionality***

Enable mouse interactivity:

`set mouse=a`

The mouse can be enabled for different modes:

Value| |description
-----|-|-----------
n    | |Normal mode and Terminal modes
v    | |Visual mode
i    | |Insert mode
c    | |Command-line mode
h    | |all previous modes when editing a help file
a    | |all previous modes
r    | |for hit-enter and more-prompt prompt

***Pane Size Constraint***

Automatically resize panes proportionately when terminal window size changes:

`au VimResized * wincmd =`

### Buffers

#### Basics

***List all open buffers***

Use the following command to list all buffers.

`:buffers`

Example Output of `:buffers`:

    1 #a   "MyFile.txt"                   line 5
    3 %a   "Some_Other_File.txt"          line 1
    4 #  + "~/.vimrc"                     line 28
    5  a   "~/plain_text_passwords.lol"   line 7

* Column 1
  * Buffer number.
* Column 2
  * The current buffer is marked by `%`.
  * An alternate buffer will be marked with `#`.
  * Active buffers, or buffers that are displayed on screen, will be marked with an `a`.  
* Column 3
  * This column will display a `+` if there are any unwritten changes in that buffer.
* Column 4
  * Filename.
* Column 5
  * Line number where the cursor is located in that buffer.

#### Delete Buffers

***Delete Current Buffer***

You will not want to use `:q` when working with multiple files as it will exit VIM entirely.

Instead, you can manage buffers with a couple of commands.

Delete Current buffer:

`:bdelete`

or:

`:bd`

#### Delete Other Buffers

***Deleting a Single Buffer***

Enter the `:bd` command and the buffer number of the buffer to be deleted.
Alternative, start typing the name of the file in the target buffer and use tab completion to finish the filename.

`:bd [<buffer number>|<file.name>]`

**Deleting Multiple Buffers**

To delete multiple buffers at once, append an "!" to the end of the `:bd` command:

`:bd! <buffer 1> <buffer 2> ...`
