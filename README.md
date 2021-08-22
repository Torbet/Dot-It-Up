# Vim It Up 🔥
### A collection of scripts, plugins, and clever hacks so that you can exit vim in STYLE! 🚀

(Not that you would want to, ever... MUAHAHAHA)

![Vim It Up](vim.png)

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](./CONTRIBUTING.md)

Some of the settings here may reference a 'leader' key, use:
```vim
let mapleader="{Your Key Of Choice}"
```

## Sane-er Defaults

Enables syntax highlighting, why wouldn't you?
```vim
syntax on
```

Shows you line numbers, it's great:
```vim
set number
```

Copy and paste from the **system** clipboard, and avoid indentation issues:
```vim
noremap <leader>y "+y
noremap <leader>p "+p
```

Makes the backspace key behave like you'd expect, and go through EVERYTHING:
```vim
set backspace=indent,eol,start
```

Makes 1 tab = 4 spaces:
```vim
set shiftwidth=4
set tabstop=4
```

Convert tabs to spaces:
```vim
set expandtab
```

Always try to show 10 lines above and below the cursor location:
```vim
set scrolloff=10
```

Allows you to switch between buffers without saving EVERY TIME:
```vim
set hidden
```

Change to the correct indention and plugins dependent on the file type
```vim
filetype on
filetype indent on
filetype plugin on
```

## KO Key-Strokes

Visually select the entire file:
```vim
ggVG
```

Search for the word under the cursor:
```vim
*
```

## Handy-Dandy Commands

Reads and inserts the contents of a file at the current line:
```vim
:r {your file name}
```

Reads and inserts the output of a shell command at the current line:
```vim
:r! {your shell command, eg: ls}
```

Find and replace "foo" with "bar" through whole file!
```vim
:%s/foo/bar/g 
```

## Remaps, Baby!

Move visual selection up and down a line:
```vim
vnoremap J :m '>+1<CR>gv=gv
vnoremap K :m '<-2<CR>gv=gv
```

## Avoiding RSI

If you use command mode a lot, swapping the colon and semi-colon keys means 1 less keypress:
```vim
nnoremap ; :
nnoremap : ;
```

Write to and exit the file, behaves like :wq:
```vim
ZZ
```

Run the current line as a command:
```vim
:<Ctrl-r> <Ctrl-l>
```

## Nicer Navigation

Allows the cursor to move up and down naturally by display, lines instead of file lines:
```vim
nnoremap j gj
nnoremap k gk
```

Make yanking with capital Y behave like the other capital letters, and yank until the end of the line:
```vim
nnoremap Y y$
```

Press space to go down 10 lines, control + space to go up 10 lines:
```vim
noremap <Space> 10j
noremap <C-Space> 10k
```

## File and Buffer Navigation (but better)

Press space twice to switch between your last two buffers, use it all the time for superfast switching:
```vim
nnoremap <leader><leader> <c-^>
```

Switch buffers with Left and Right arrow keys:
```vim
nnoremap <left> :bp<cr>
nnoremap <right> :bn<cr>
```

## Text searching

Search for foo throughout file (press n for next, N for previous):
```vim
/foo
```

Searching ignores case unless an upper case letter is present in the query:
```vim
set ignorecase smartcase
```

Begin searching while typing, highlighting matches:
```vim
set incsearch hlsearch
```

Press your 'leader' key + enter to clear search highlighting:
```vim
nnoremap <silent> <leader><CR> :noh<CR>
```

## Super-Cool Plugins

A fuzzy-finder to easily search for files, contents & buffers:

[junegunn/fzf.vim](https://github.com/junegunn/fzf.vim)

Provides mappings to easily delete, change and add parentheses, brackets, quotes, and tags:

[tpope/vim-surround](https://github.com/tpope/vim-surround)

An integrated git experience in vim, that's "so awesome, it should be illegal":

[tpope/vim-fugitive](https://github.com/tpope/vim-fugitive)
