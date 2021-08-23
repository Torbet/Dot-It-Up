# Dot It Up 🔥
### A collection of dotfile scripts, plugins, and clever hacks so that you can become the master of your own OS!

![Dot It Up](vim.png)

[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](./CONTRIBUTING.md)

# Table Of Contents

<!-- toc -->

- [Popular Dotfiles](#popular-dotfiles)
- [Vim](#vim)
  * [Sane-er Defaults](#sane-er-defaults)
  * [KO Key-Strokes](#ko-key-strokes)
  * [Handy-Dandy Commands](#handy-dandy-commands)
  * [Remaps, Baby!](#remaps-baby)
  * [Avoiding RSI](#avoiding-rsi)
  * [Nicer Navigation](#nicer-navigation)
  * [File and Buffer Navigation (but better)](#file-and-buffer-navigation-but-better)
  * [Text searching](#text-searching)
  * [Super-Cool Plugins](#super-cool-plugins)
  * [ColorSchemes](#colorschemes)
- [TMUX](#tmux)
  * [Better Life, From the Start!](#better-life-from-the-start)
  * [Plugins That Rock!](#plugins-that-rock)
- [Shell (ZSH & Bash)](#shell-zsh--bash)
  * [Oh-My-ZSH](#oh-my-zsh)
  * [Gnarly Plugs, Man](#gnarly-plugs-man)

<!-- tocstop -->

# Popular Dotfiles

* [holman](https://github.com/holman/dotfiles) - @holman does dotfiles
* [LukeSmithxyz](https://github.com/LukeSmithxyz/voidrice) - My dotfiles (deployed by LARBS)
* [mathiasbynens](https://github.com/mathiasbynens/dotfiles) - :wrench: .files, including ~/.macos — sensible hacker defaults for macOS
* [lewagon](https://github.com/lewagon/dotfiles) - Default configuration for Le Wagon's students
* [jessfraz](https://github.com/jessfraz/dotfiles) - My dotfiles. Buyer beware ;)
* [cowboy](https://github.com/cowboy/dotfiles) - My Ubuntu / OS X dotfiles.
* [amacgregor](https://github.com/amacgregor/dot-files) - Dotfiles repository
* [alrra](https://github.com/alrra/dotfiles) - 💻 macOS / Ubuntu dotfiles
* [CoreyMSchafer](https://github.com/CoreyMSchafer/dotfiles) - My dotfiles and personal preferences
* [justone](https://github.com/justone/dotfiles) - Dotfiles
* [webpro](https://github.com/webpro/awesome-dotfiles) - A curated list of dotfiles resources.
* [thoughtbot](https://github.com/thoughtbot/dotfiles) - A set of vim, zsh, git, and tmux configuration files.
* [driesvints](https://github.com/driesvints/dotfiles) - Get started with your own dotfiles.
* [TheLocehiliosan](https://github.com/TheLocehiliosan/yadm) - Yet Another Dotfiles Manager
* [skwp](https://github.com/skwp/dotfiles) - YADR - The best vim,git,zsh plugins and the cleanest vimrc you've ever seen
* [anishathalye](https://github.com/anishathalye/dotbot) - A tool that bootstraps your dotfiles ⚡️
* [theniceboy](https://github.com/theniceboy/.config) - My dotfiles
* [paulirish](https://github.com/paulirish/dotfiles) - paul's shell, git, etc config files. also homebrew, migration setup. good stuff.
* [webpro](https://github.com/webpro/dotfiles) - Dotfiles for macOS
* [awesome-streamers](https://github.com/awesome-streamers/awesome-streamerrc) - Dotfiles for various streamers on Twitch.
* [dotphiles](https://github.com/dotphiles/dotphiles) - A community driven framework of dotfiles.
* [fatih](https://github.com/fatih/dotfiles) - My personal dotfiles
* [jessfraz](https://github.com/jessfraz/.vim) - My .vim dotfiles and configurations.
* [freekmurze](https://github.com/freekmurze/dotfiles) - My personal dotfiles
* [joedicastro](https://github.com/joedicastro/dotfiles) - My .dotfiles
* [michaeljsmalley](https://github.com/michaeljsmalley/dotfiles) - My dotfiles
* [freshshell](https://github.com/freshshell/fresh) - Keep your dotfiles fresh.
* [jaagr](https://github.com/jaagr/dots) - dotfiles for my local setup
* [spencerwooo](https://github.com/spencerwooo/dotfiles) - Dotfiles for all :D
* [twpayne](https://github.com/twpayne/chezmoi) - Manage your dotfiles across multiple diverse machines, securely.

# Vim

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

Case insensitive in `command-line` mode:
```vim
set wildignorecase
```

Change to the correct indention and plugins dependent on the file type
```vim
filetype on
filetype indent on
filetype plugin on
" or one line alternative
filetype plugin indent on
```

## KO Key-Strokes

### Normal mode

Visually select the entire file:
```vim
ggVG
```

Search for the word under the cursor (forward):
```vim
*
```

Search for the word under the cursor (backward):
```vim
#
```

Re-run the last `command-line` command:
```vim
@:
```

### Insert mode

Alternative to `Esc`:
```vim
<C-[>
```

Paste the content of register and fix the indent:
```vim
<C-r><C-p><vim-register>
" for example: <C-r><C-p>+ (paste clipboard content into vim)
```

Delete until the beginning of recently added word:
```vim
<C-w>
```

Delete until the beginning of where entering insert mode:
```vim
<C-u>
```

### Visual mode

Add/minus number for each matching line:
```vim
g<C-a> " add one number
g<C-x> " minus one number
" for example:
" select the number below using Visual block command:
" 0
" 0
" 0
" if we use g<C-a>, then those three line will become:
" 1
" 2
" 3
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
Quickly re-select either the last pasted or changed text:
```vim
noremap gV `[v`]
```

Run the recorded macro on a range of lines:

```vim
" Credit goes to https://github.com/stoeffel/.dotfiles/blob/master/vim/visual-at.vim
xnoremap <silen> @ :<C-u>echo "@".getcmdline() | execute ":\'<,\'>normal @" . nr2char(getchar())<CR>
```

## Avoiding RSI

If you use command mode a lot, swapping the colon and semi-colon keys means 1 less keypress:
```vim
nnoremap ; :
nnoremap : ;
```

Write to and exit the file, behaves like `:wq`:
```vim
ZZ
```

Exit without saving, behaves like `:q!`:
```vim
ZQ
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
" if there's an issue with ctrl-space, you can use <C-@> or <Nul>
" Ref: https://stackoverflow.com/a/24983736
noremap <C-@> 10k
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

Vim like navigation of file system using buffers.

[justinmk/vim-dirvish](https://github.com/justinmk/vim-dirvish)

## ColorSchemes

* [vim-colors-solarized](https://github.com/altercation/vim-colors-solarized) - precision colorscheme for the vim text editor
* [vim](https://github.com/challenger-deep-theme/vim) - FlatColor vim colorscheme
* [vim-one](https://github.com/rakr/vim-one) - Adaptation of one-light and one-dark colorschemes for Vim
* [jellybeans.vim](https://github.com/nanotech/jellybeans.vim) - A colorful, dark color scheme for Vim.
* [vim-github-colorscheme](https://github.com/endel/vim-github-colorscheme) - A vim colorscheme based on Github's syntax highlighting.
* [onedark.vim](https://github.com/joshdick/onedark.vim) - A dark Vim/Neovim color scheme inspired by Atom's One Dark syntax theme.
* [Apprentice](https://github.com/romainl/Apprentice) - A dark, low-contrast, Vim colorscheme.
* [srcery-vim](https://github.com/srcery-colors/srcery-vim) - Dark colorscheme for gvim and vim
* [vim-janah](https://github.com/mhinz/vim-janah) - Vim colorscheme.
* [tender.vim](https://github.com/jacoborus/tender.vim) - A 24bit colorscheme for Vim, Airline and Lightline
* [Alduin](https://github.com/AlessandroYorba/Alduin) - A Vim Colorscheme
* [vim-solarized8](https://github.com/lifepillar/vim-solarized8) - Optimized Solarized colorschemes. Best served with true-color terminals!
* [vim-colorscheme-primary](https://github.com/google/vim-colorscheme-primary) - Primary, a Vim color scheme based on Google's colors
* [vim-vividchalk](https://github.com/tpope/vim-vividchalk) - vividchalk.vim: a colorscheme strangely reminiscent of Vibrant Ink for a certain OS X editor
* [nvcode-color-schemes.vim](https://github.com/ChristianChiarulli/nvcode-color-schemes.vim) - A bunch of generated colorschemes (treesitter supported)
* [vim-afterglow](https://github.com/danilo-augusto/vim-afterglow) - Vim adaptation of the Afterglow colorscheme
* [desert.vim](https://github.com/fugalh/desert.vim) - desert colorscheme
* [wal.vim](https://github.com/dylanaraps/wal.vim) - 🎨 A vim colorscheme for use with wal
* [Sierra](https://github.com/AlessandroYorba/Sierra) - A Vim Colorscheme
* [vim-gruvbox8](https://github.com/lifepillar/vim-gruvbox8) - A simplified and optimized Gruvbox colorscheme for Vim
* [space-vim-dark](https://github.com/liuchengxu/space-vim-dark) - :purple_heart: A dark colorscheme for space-vim, see space-vim-theme for light background support!
* [vim-kalisi](https://github.com/freeo/vim-kalisi) - The colorscheme with neovim in mind
* [candid.vim](https://github.com/flrnd/candid.vim) - A dark colorscheme with vibrant colors
* [anderson.vim](https://github.com/tlhr/anderson.vim) - Dark vim colorscheme based on colors from Wes Anderson films
* [kuroi.vim](https://github.com/aonemd/kuroi.vim) - A very dark colorscheme for Vim
* [landscape.vim](https://github.com/itchyny/landscape.vim) - A colorscheme for Vim
* [nord-vim](https://github.com/arcticicestudio/nord-vim) - An arctic, north-bluish clean and elegant Vim theme.
* [vim-monotone](https://github.com/Lokaltog/vim-monotone) - A dark, monochrome colorscheme for vim


# TMUX

Most of the settings here require a prefix key, use this to set it, or keep it as ctrl+b, it's your life ;)
```tmux
unbind C-b
set -g prefix {Your Key Of Choice}
```

## Better Life, From the Start!

Tmux Windows start from 1, so no big reaches ;)
```tmux
set -g base-index 1
```

Makes keys register instantly, you may notice escape delays in vim without this:
```tmux
set -s escape-time 0
```

Prefix+c will open a new tmux session in your current directory:
```tmux
bind c new-window -c "#{pane_current_path}"
```

Renumber windows sequentially after closing any of them:
```tmux
set -g renumber-windows on
```

Enable mouse, it's sometimes nice for scrolling:
```tmux
set -g mode-mouse on
```

Increase scroll-back history, so you can see more:
```tmux
set -g history-limit 10000
```

## Plugins That Rock!

Installing TPM (Tmux plugin manager):
```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

A set of tmux options that should be acceptable to everyone.
[tmux-sensible](https://github.com/tmux-plugins/tmux-sensible)

# Shell (ZSH & Bash)

## Oh-My-ZSH

Gives you more customization over your shell

Install:
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

Add to zshrc:
```bash
ZSH=~/.oh-my-zsh
```

## Gnarly Plugs, Man

Auto-complete shell commands, it's cool:

[zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)

Highlight your current command, lets you know what's going on:

[zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)
