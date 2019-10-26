# VIM Cheat Sheet

## Table of Contents

1. [VIM Cheat Sheet](#vim-cheat-sheet)
   1. [Table of Contents](#table-of-contents)
2. [.vimrc Magic](#vimrc-magic)
3. [Buffers](#buffers)
   1. [List all open buffers](#list-all-open-buffers)
   2. [Delete Buffers](#delete-buffers)
   3. [Delete Other Buffers](#delete-other-buffers)
   4. [Switch Buffers](#switch-buffers)
4. [Split Panes](#split-panes)
5. [Visual Mode](#visual-mode)
6. [Search and Replace](#search-and-replace)
7. [Diff](#diff)
8. [Copy and Paste](#copy-and-paste)


# .vimrc Magic

Check if file has been changed externally and reload into buffer

`au FocusGained,BufEnter * :silent! checktime`


Auto-save on window focus is lost

`au FocusLost,WinLeave * :silent! w`


Enable mouse interactivity

`set mouse=a`

The mouse can be enabled for different modes: 
n        Normal mode and Terminal modes
v        Visual mode 
i         Insert mode
c        Command-line mode
h        all previous modes when editing a help file
a        all previous modes
r        for hit-enter and more-prompt prompt


Automatically resize panes proportionately when terminal window size changes

`au VimResized * wincmd =`



# Buffers

## List all open buffers

Use the following command to list all buffers.

`:buffers`

Example Output of :buffers
```
  1 #a   "MyFile.txt"                   line 5
  3 %a   "Some_Other_File.txt"          line 1
  4 #  + "~/.vimrc"                     line 28
  5  a   "~/plain_text_passwords.lol"   line 7
```
The first column shows the buffer number.

The second column will indicate if the file is active (displayed on screen) and is denoted with "a".  
The currently focused buffer is marked by `%`.  A buffer marked with `#` is a little trickier... I'll get back to on that one.

The third column will show a `+` if there are any unwritten changes in that buffer.

The fourth column is filename of course.

The fifth column indicates the line number where the cursor is located in that buffer.


## Delete Buffers 
You will not want to use `:q` when working with multiple files as it will exit VIM entirely. Instead, you can manage buffers with a couple of commands.

Delete Current buffer

`:bdelete`

or 

`:bd`

## Delete Other Buffers

**Deleting a Single Buffer**

Enter the `:bd` command and the buffer number of the buffer to be deleted. Alternative, start typing the name of the file in the target buffer and use tab completion to finish the filename.
```
:bd [<buffer number>|<file.name>]
```


**Deleting Multiple Buffers**

To delete multiple buffers at once, append an "!" to the end of the `:bd` command.

`:bd! <buffer 1> <buffer 2> ...`



## Switch Buffers

```
```


# Split Panes

```
```


# Visual Mode

```
```


# Search and Replace

```
```


# Diff

```
```

# Copy and Paste

```
```
