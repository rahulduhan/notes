
# VIM tutor summary

### Lesson 1 SUMMARY

 1. The cursor is moved using either the arrow keys or the hjkl keys.
     h (left)   j (down)       k (up)       l (right)

 2. To start Neovim from the shell prompt type:
~~~ sh
    $ nvim FILENAME
~~~
 3. To exit Neovim type: `<Esc>`{normal} `:q!`{vim} `<Enter>`{normal} to trash all changes.
                OR type: `<Esc>`{normal} `:wq`{vim} `<Enter>`{normal} to save the changes.

 4. To delete the character at the cursor type: `x`{normal}

 5. To insert or append text type:
    `i`{normal} insert text `<Esc>`{normal}     insert before the cursor.
    `A`{normal} append text `<Esc>`{normal}     append after the line.

NOTE: Pressing `<Esc>`{normal} will place you in Normal mode or will cancel
      an unwanted and partially completed command.

### Lesson 2 SUMMARY

 1. To delete from the cursor up to the next word type:    `dw`{normal}

 2. To delete from the cursor to the end of a line type:   `d$`{normal}

 3. To delete a whole line type:                           `dd`{normal}

 4. To repeat a motion prepend it with a number:           `2w`{normal}

 5. The format for a change command is:

        operator   [number]   motion

    where:

        operator -   is what to do, such as [d](d) for delete
        [number] -   is an optional count to repeat the motion
        motion   -   moves over the text to operate on, such as:
                        [w](w) (word),
                        [$]($) (to the end of line), etc.

 6. To move to the start of the line use a zero: [0](0)

 7. To undo previous actions, type:            `u`{normal}  (lowercase u)
    To undo all the changes on a line, type:   `U`{normal}  (capital U)
    To undo the undo's, type:                  `<C-r>`{normal}

### Lesson 3 SUMMARY

 1. To put back text that has just been deleted, type [p](p). This puts the
    deleted text AFTER the cursor (if a line was deleted it will go on the
    line below the cursor).

 2. To replace the character under the cursor, type [r](r) and then the
    character you want to have there.

 3. The [change operator](c) allows you to change from the cursor to where
    the motion takes you. Type `ce`{normal} to change from the cursor to the
    end of the word, `c$`{normal} to change to the end of a line, etc.

 4. The format for change is:

        c   [number]   motion

### Lesson 4 SUMMARY

 1. `<C-g>`{normal}     displays your location and the file status.
    `G`{normal}         moves to the end of the file.
    number `G`{normal} moves to that line number.
    `gg`{normal}        moves to the first line.

 2. Typing `/`{normal} followed by a phrase searches FORWARD for the phrase.
    Typing `?`{normal} followed by a phrase searches BACKWARD for the phrase.
    After a search type `n`{normal} to find the next occurrence in the same
    direction or `N`{normal} to search in the opposite direction.
    `<C-o>`{normal} takes you back to older positions, `<C-i>`{normal} to
    newer positions.

 3. Typing `%`{normal} while the cursor is on a (,),[,],{, or } goes to its
    match.

 4. To substitute new for the first old in a line type
~~~ vim
        :s/old/new
~~~
    To substitute new for all 'old's on a line type
~~~ vim
        :s/old/new/g
~~~
    To substitute phrases between two line ###'s type
~~~ vim
        :###,###s/old/new/g
~~~
    To substitute all occurrences in the file type
~~~ vim
        :%s/old/new/g
~~~
    To ask for confirmation each time add 'c'
```vim
		:%s/old/new/gc
```

### Lesson 5 SUMMARY

 1. [:!command](:!vim) executes an external command.

     Some useful examples are:
     `:!ls`{vim}                    - shows a directory listing
     `:!rm FILENAME`{vim}           - removes file FILENAME

 2. [:w](:w) FILENAME              writes the current Neovim file to disk with
                             name FILENAME.

 3. [v](v)  motion  :w FILENAME   saves the Visually selected lines in file
                             FILENAME.

 4. [:r](:r) FILENAME              retrieves disk file FILENAME and puts it
                             below the cursor position.

 5. [:r !dir](:r!)                  reads the output of the dir command and
                             puts it below the cursor position.

### Lesson 6 SUMMARY

 1. Type `o`{normal} to open a line BELOW the cursor and start Insert mode.
    Type `O`{normal} to open a line ABOVE the cursor.

 2. Type `a`{normal} to insert text AFTER the cursor.
    Type `A`{normal} to insert text after the end of the line.

 3. The `e`{normal} command moves to the end of a word.

 4. The `y`{normal} operator copies text, `p`{normal} pastes it.

 5. Typing a capital `R`{normal} enters Replace mode until `<Esc>`{normal} is
     pressed.

 6. Typing "[:set](:set) xxx" sets the option "xxx". Some options are:

        'ic' 'ignorecase'   ignore upper/lower case when searching
        'is' 'incsearch'    show partial matches for a search phrase
        'hls' 'hlsearch'    highlight all matching phrases

     You can either use the long or the short option name.

 7. Prepend "no" to switch an option off:
~~~ vim
        :set noic
~~~
 8. Prepend "inv" to invert an option:
~~~ vim
        :set invic
~~~

### Lesson 7 SUMMARY

 1. Type `:help`{vim}
    or press `<F1>`{normal} or `<Help>`{normal} to open a help window.

 2. Type `:help TOPIC`{vim} to find help on TOPIC.

 3. Type `<C-w><C-w>`{normal} to jump to another window

 4. Type `:q`{vim} to close the help window

 5. Create an init.vim startup script to keep your preferred settings.

 6. While in command mode, press `<C-d>`{normal} to see possible completions.
    Press `<Tab>`{normal} to use one completion.



###### VIM Notes from VIM Tutor by Luke Smith
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
```