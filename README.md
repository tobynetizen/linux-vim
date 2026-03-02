## Vim Configuration
The following code serves as the base configuration for basic navigation and usage for common plugins.
For a list of all options, or if you wish to learn more, type `:options` or click [here](https://vimdoc.sourceforge.net/htmldoc/options.html).
<br>
```vim
syntax enable
set hidden
set nowrap
set encoding=utf-8
set pumheight=10
set fileencoding=utf-8
set ruler
set cmdheight=2
set iskeyword+=-
set mouse=a
set splitbelow
set splitright
set t_Co=256
set conceallevel=0
set tabstop=4
set shiftwidth=4
set smarttab
set expandtab
set smartindent
set autoindent
set laststatus=2
set number
set cursorline
set background=dark
set showtabline=2
set noshowmode
set nobackup
set nowritebackup
set updatetime=300
set timeoutlen=500
set formatoptions-=cro
set clipboard=unnamedplus
set nocompatible
filetype off
au! BufWritePost $MYVIMRC source %
set termguicolors
```
The following code should install Vundle, which will allow you to run `:PlugInstall` to install the rest of the plugins, and `:PlugUpdate` to check for updates when available for all installed plugins.
<br>
```vim
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

Plugin 'VundleVim/Vundle.vim'
Plugin 'itchyny/lightline.vim'
Plugin 'arcticicestudio/nord-vim'
Plugin 'neoclide/coc.nvim', { 'branch': 'master', 'do': 'npm ci' }

call vundle#end()
filetype plugin indent on
```
The following code should enable the Nord theme which will require a terminal restart to take effect.
<br>
```vim
let g:lightline = {
\ 'colorscheme': 'nord',
\ }

colorscheme nord
```
To install language servers in CoC, simply run `:CocInstall` followed by the language server extension.
For example, installing a Bash language server: `:CocInstall coc-sh`
For a list of supported extensions and language servers, click [here](https://github.com/neoclide/coc.nvim/wiki/Using-coc-extensions#implemented-coc-extensions).
<br>
If you wish to replicate the code navigation in Visual Studio Code, add this to your configuration:
<br>
```vim
nmap <silent><nowait> gd <Plug>(coc-definition)
nmap <silent><nowait> gy <Plug>(coc-type-definition)
nmap <silent><nowait> gi <Plug>(coc-implementation)
nmap <silent><nowait> gr <Plug>(coc-references)
```
