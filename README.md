# vimrc
my vim config


```bash

syntax on

filetype plugin indent on
set tabstop=4
set shiftwidth=4
set softtabstop=4
set autoindent
set smartindent
set mouse=a
set splitbelow
set number
set autoread
let g:dracula_italic = 0

nnoremap <C-a> ggVG
vmap <C-z> "+y

autocmd filetype cpp nnoremap <F5> :w<bar>term ++shell g++ -o compile %:p && ./compile<CR>
autocmd filetype python nnoremap <F5> :w<bar>term ++shell python %:p<CR>

nnoremap ss i#include<bits/stdc++.h><CR>using namespace std;<CR><CR>void solve(){<CR><CR><CR><Cr>}<Esc>o<CR>signed main(){<CR>ios_base::sync_with_stdio(0), cin.tie(0), cout.tie(0);<CR><CR>int t = 1;<CR>cin >> t;<CR>while(t--) solve(), cout << '\n';<CR><CR>return 0;<CR>}

call plug#begin()


Plug 'neoclide/coc.nvim'
Plug 'jiangmiao/auto-pairs'
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'preservim/nerdtree'
Plug 'dracula/vim', { 'as': 'dracula' }

call plug#end()

function! CheckBackspace() abort
let col = col('.') - 1
return !col || getline('.')[col - 1]  =~# '\s'
endfunction

inoremap <silent><expr> <Tab>
\ coc#pum#visible() ? coc#pum#next(1) :
\ CheckBackspace() ? "<Tab>" :
\ coc#refresh()
set termguicolors

inoremap <c-b> <Esc>:NERDTreeToggle<cr>
nnoremap <c-b> <Esc>:NERDTreeToggle<cr>noremap <c-b> <Esc>:NERDTreeToggle<cr>


if exists('$TMUX')
let &t_7f = "<Esc>[38;2;%lu;%lu;%lum"
let &t_7b = "<Esc>[48;2;%lu;%lu;%lum"
endif

colorscheme dracula



```
