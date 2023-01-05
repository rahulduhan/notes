## VIM Notes from VIM Tutor 
```vim
gj " to move to next visual line
gk " to move to previous visual line
```
```vim
zz 		" to middle of the page
zt            " to top of the page
zb            " to bottom of the page
```

```vim
daw      " delete around the word
diw      " delete inside the word
das      " delete around sentence
```

```vim
:s/text/replace/g   " to substitue word globally in the selected line
:%s/text/replace/g  " to substitue word globally in the whole file
:%s/text/replace/gc " same as above, c asks for confirmation for each word
```

```vim
:x              " equivalent to wq
 
```
```vim
``              " to go back to previous position
%               " to jump to maching parenthesis
<Ctrl + o>      " to go back in position history
<Ctrl + i>      " to go forward in position history
```

```vim
:!___       " to execute external commands 
:r          " reads the output of comman or a file and puts it in working files for eg.
:r TEST     " prints the file with name TEST in the working file
:r !ls      " prints the output of ls in the working file
```

```vim
:norm           " to run a sequence on selected line
```

```vim
<Ctrl + u>      " up half a page
<Ctrl + d>      " down half a page
<Ctrl + g>      " info about the page
```

```vim
H " move at top of the page
M " move at middle of the page
L " move at low of the page
```

```vim
.               " redo last command
v               " visual mode
:set ic         " ignore case
:set hlsearch   " highlighted search
```

```vim 
235 G            " to go to line no 235
```

```vim
cw               " change word
c$ or C          " change to the end of the line
```j