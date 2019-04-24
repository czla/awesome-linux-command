# Vim command tutorial
For Chinese version, click [中文版](Vim.md)  

## Content 
* [1.Cursor Movement](#1cursor-movement)
* [2.Basic Editing](#2basic-editing)
* [3.Search and replace](#3search-and-replace)

### 1.Cursor Movement

Key | Description  
:-: | :-  
`l`or`Right`| Right one character
`h`or`Left`| Left one character
`j`or`Down`| Down one line
`k`or`Up`| Up one line
`0` | To the beginning of the current line
`^` | To the first non-whitespace character on the current line
`$` | To the end of the current line
`w` | To the beginning of the next word or puntuation character
`W` | To the beginning of the next word, ignoring puntuation character
`b` | To the beginning of the previous word or punctuation character
`B` | To the beginning of the previous word, ignoring punctuation characters
`Ctrl-f`or`PgDown` | Down one page
`Ctrl-b`or`PgUp` | Up one page
number`G` | To line number. For example, 1G moves to the first line of the file
`G` | To the last line of the file

[Back to Content](#content)

### 2.Basic Editing

* Append and undo text

Key | Description
:-: | :-  
`i` | inset text before the cursor
`a` | inset text behind the cursor
`o` | Opens the line below the current line
`O` | Opens the line below the current line
`u` | Undo the change

* Delete command

Key | Description
:-: | :-  
`x` | Deletes the current character
`3x` | Deletes the current character and the next two character
`dd` | Deletes the current line
`5dd` | Deletes the current line and the next four lines
`dW` | Deletes from the cursor position to the beginning of the next word
`d$` | Deletes from the cursor position to the end of the current line
`do` | Deletes from the cursor position to the beginning of the current line
`d^` | Deletes from the cursor position to the first non-whitespace character of the line
`dG` | Deletes from the current line to the end of the file
`d20G` | Deletes from the current line to the twentieth line of the file

* Copy command

Key | Description
:-: | :-  
`yy` | Copies the current line
`5yy` | Copies the current line and the next four lines
`yW` | Copies from the current cursor position to the beginning of the next word
`y$` | Copies from the current cursor location to the end of the current line
`y0` | Copies from the current cursor location to the beginning of the line
`y^` | Copies from the current cursor location to the first non- whitespace character in the line
`yG` | Copies from the current line to the end of the file
`y20G` | Copies from the current line to the twentieth line of the file

* Paste command

Key | Description
:-: | :-  
`p` | paste the line below the current line
`P` | paste the text above the current line
[Back to Content](#content)

### 3.Search And Replace

Command | Description
:-: | :-
`:%s/Line/line/gc` | change the word “Line” to “line” for the entire file under user's confirmation
`:` | the colon character starts an ex command
`%` | specifies the range of lines for the operation. % means "from the first line to the last line"；and 1,$ means“from line 1 to the last line in the file”.If the range of lines is omitted, the operation is only performed on the current line.
`s` | specifies the operation. In this case, substitution (search and replace)
`/Line/line` | the search pattern and the replacement text
`g` |  “global”, the search and replace is performed on every instance of the search string in the line. If omitted, only the first instance of the search string on each line is replaced
`c` | with user confirmation，If omitted, replace straightly

with user confirmation：`replace with Line (y/n/a/q/l/^E/^Y)?`，usr do the following confirm  

Key | Description
:-: | :-  
`y` | perform the substitution
`n` | skip this instance of the pattern
`a` | perform the substitution on this and all subsequent instances of the pattern
`q or ESC` | quit the substitution
`l` | perform this substitution and then quit. Short for"last"
`Ctrl-e`or`Ctrl-y` | scroll down and scroll up, respectively. Useful for viewing the context of the proposed substitution

[Back to Content](#content)