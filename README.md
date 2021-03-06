# Vim Handbook

My shortcuts and notes on vim

## Cursor navigation

- To move the cursor, press the h,j,k,l keys as indicated:

```shell
      ^
      k              Hint:  The h key is at the left and moves left.
< h       l >               The l key is at the right and moves right.
      j                     The j key looks like a down arrow.
      v
```

- `H` – screen top;
- `L` – screen bottom;
- `w` – to the beginning of a next word. `W` – same, but punctuation as a word;
- `e` – to the end of a word. `E` – same, but punctuation as a word;
- `b` – to the beginning of a current or previous word. `B` – same, but punctuation as a word;
- `*`/`#` – search forward/backward for the word nearest to the cursor.
- `%` – switching between paired brackets;
- `f`, `F` – find a character. Move on a character. A letter case switches the direction;
- `t`, `T` – till a character. Move before a character. A letter case switches the direction;
- `0` – start of a line;
- `$` – end of a line;
- `^` – first character of a line. Same as `0w`;
- `{`, `}` – begin and end of a paragraph;
- `CTRL u`/`CTRL d` – half-screen up/down;
- `CTRL b`/`CTRL f` – page up/down.

## Scroll

- `CTRL y`/`CTRL e` – scroll one line up/down;
- `zz` – current line at the center of a window;
- `zb` – current line at the bottom of a window;
- `zt` – current line at the top of a window;

more [here](http://vimdoc.sourceforge.net/htmldoc/scroll.html#scroll-cursor)

## Macroses

- `q[macros key][actions]q` – record macros
- `@[macros key]` – play macros

## Clipboard

- `y` – yank. Works as `CTRL c`;
- `yy` – copy current line;
- `d` – last thing you deleting is getting stored at the clipboard;
- `p` – place after the cursor. `P` – place before cursor;

## Registers

Registers allow you to have multiple clipboards bound on any key.

- `"[name]yy` – copy a line into [name] register
- `"[name]p` – paste a content of [name] register

## Edit without insert mode

- `x` – delete current symbol
- `r` – replace current symbol
- `R` – replace many symbols. Replace mode.
- `J` – join next line to current
- `>` `<` – indentation
- `dd` – delete current line
- `dw` – delete till the start of a next word;
- `de` – delete to the end of a word only;
- `diw` – delete current word;
- `dt[character],`dT[character]` – delete till character
- `df[character],`dF[character]` – delete including character

## Enter insert mode

- `i` – enter before the cursor;
- `a` – enter after the cursor;
- `o` – enter from a new line below the current;
- `O` – enter from a new line above the current;

## Insert mode

- `CTRL h` – delete the character before the cursor
- `CTRL w` – delete the word before the cursor
- `CTRL o` – switches to normal mode for one command

## Change mode

Delete part of a text and enter insert mode.

##### Line scope:

- `C` – change before cursor to the end of a line. Same as `c$`;
- `c0` – change before cursor to the start of a line;
- `S` or `cc` – change the whole line;

##### Word scope:

- `ciw` – change the whole word no matter where the cursor;
- `cw` or `ce` – works almost the same. The exception occurs only in case of one symbol word or space;
  > From [Reddit](https://www.reddit.com/r/vim/comments/26nut8/why_does_cw_work_like_ce/):<br>
  > cw is NOT the same as ce. If the cursor is on the last char of a word (or a single-char word), ce extends to the next end-of-word, while cw only works on the one character. Also, if your cursor is on whitespace, cw behaves on the same range as dw.

##### Define character:

- `ct[character]`, `cT[character]` – change till character; A letter case switches the direction;
- `cf[character]`, `cF[character]` – change including character. A letter case switches the direction;

##### Search related

- `cgn`, `cgN` – change based on your last search. A letter case switches the direction;

## Visual mode

- `v` – visual mode. Select characters;
- `V` – visual lines mode. Select lines;
- `CTRL v` – select block. Useful for editing multiple lines.

## Search

- `/[search term]` – search through a file toward the bottom;
- `?[search term]` – search through a file toward the top;
- `n`, `N` – navigate through found items;

## Replace

- `s/[term to replace]/[new term]/g` – replace all terms withing a current line. Remove `g` flag to replace one term;
- `%s/[term to replace]/[new term]` – replace all found terms withing a file;

## Case sensitivity

- `/\C[search term]` – case sensitive search;
- `/\c[search term]` – case insensitive search;
- `:set ignorecase` or `:set ic` – insensitive by default;
- `:set smartcase` or `:set noic` – sensitive by default;

## Misc

- `:q` – quit
- `:q!` – quit without save
- `:w` – write changes
- `:wq` or `ZZ` – write changes and quit
