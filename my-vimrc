set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" alternatively, pass a path where Vundle should install plugins
"call vundle#begin('~/some/path/here')

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'
"==== 我添加的====
Plugin 'Taglist.vim'
Plugin 'The-NERD-tree'
Plugin 'OmniCppComplete'
Plugin 'Valloric/YouCompleteMe'
Plugin 'ctrlp.vim'
Plugin 'a.vim'
Plugin 'SirVer/ultisnips'
Plugin 'EasyMotion'
Plugin 'scrooloose/nerdcommenter'
Plugin 'powerline/powerline'
Plugin 'delimitMate.vim'
Plugin 'Chiel92/vim-autoformat'
Plugin 'xolox/vim-misc'
Plugin 'xolox/vim-easytags'
Plugin 'altercation/vim-colors-solarized'

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required
" To ignore plugin indent changes, instead use:
"filetype plugin on
"
" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal
"
" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line

""""""""""以上是vbundle的设置，下面是我自己的设置""""""""
let mapleader = ","

"=== Switching between window ===
nnoremap <C-h> <C-W>h
nnoremap <C-j> <C-W>j
nnoremap <C-k> <C-W>k
nnoremap <C-l> <C-W>l
map <leader>q <C-W>q
inoremap <C-h> <Esc><C-W>h
inoremap <C-j> <Esc><C-W>j
inoremap <C-k> <Esc><C-W>k
inoremap <C-l> <Esc><C-W>l

set number "显示行号
set cursorline "显示光标
"set cursorcolumn
"autocmd BufWritePost $MYVIMRC source $MYVIMRC " 让配置变更立即生效
set helplang=cn "中文帮助
set incsearch "输入的时候就开始查找
set ignorecase "搜索时大小写不敏感
"有色彩的时候激活搜索高亮显示
if &t_Co > 2 || has("gui_running")
    syntax on
    set hlsearch
endif
set nocompatible "关闭与vi不兼容模式
set backspace=indent,eol,start "enable mac to delete
set autoindent "自动对齐
set smartindent "自动对齐
"在覆盖一个文件前，先备份
"if has("vms")
"    set nobackup
"else
"    set backup
"endif
set ruler "在vim窗口右下角显示当前光标位置
set showcmd "显示未完成的命令
filetype plugin indent on "文件类型探测
"set mouse=a "使能鼠标
set cindent shiftwidth=4 "设置shift为4个空格
set expandtab " 将制表符扩展为空格
set tabstop=4 " 设置编辑时制表符占用空格数
set shiftwidth=4 " 设置格式化时制表符占用空格数
set softtabstop=4 " 让 vim 把连续数量的空格视为一个制表符
runtime! ftplugin/man.vim "启动man插件
"colorscheme railscasts "设置主题
set comments=s1:/*,mb:*,ex:*/ "设置注释格式

"=== Taglist setting ===
map <leader>tl :TlistToggle<cr>
map <leader>tu :TlistUpdate<cr>
let Tlist_Ctags_Cmd='/usr/local/bin/ctags'
"let Tlist_Auto_Open=1
let Tlist_GainFocus_On_ToggleOpen = 1
let Tlist_Close_On_Select = 1
let Tlist_Show_One_File=1
let Tlist_Exit_OnlyWindow=1
"let tlist_cpp_settings = 'c++;c:class;f:function' "to list only the classes and functions defined
"let tlist_c_settings = 'c;f:My Functions' "to list only functions
let Tlist_Use_Right_Window = 1 "show on right

"=== ctags set ===
set tags+=~/.vim/tags/c++ "标准c++库tags
set tags+=~/C/color/tags
"=== easytags ===
set tags=./tags;
let g:easytags_dynamic_files = 1


"=== omnicppcomplete ======
set nocp
filetype plugin on
let OmniCpp_ShowPrototypeInAbbr = 1

"=== YouCompleteMe ===
let g:ycm_global_ycm_extra_conf = '~/.vim/bundle/YouCompleteMe/.ycm_extra_conf.py'
let g:ycm_seed_identifiers_with_syntax=1 "关键字补全
let g:ycm_complete_in_comments=1
let g:ycm_collect_identifiers_from_tags_files=1
let g:syntastic_error_symbol = 'x'
let g:syntastic_warning_symbol = '⚠'

" 跳转到定义的地方
nnoremap <leader>jd :YcmCompleter GoToDefinitionElseDeclaration<CR>
inoremap <leader><leader> <C-x><C-o>

"=== snipptes===
let g:UltiSnipsSnippetDirectories = ["mysnippets"]
" UltiSnips 的 tab 键与 YCM 冲突，重新设定
let g:UltiSnipsExpandTrigger="<leader><tab>"
let g:UltiSnipsJumpForwardTrigger="<leader><tab>"
let g:UltiSnipsJumpBackwardTrigger="<leader><s-tab>"

"=== 保存和恢复环境 ===
"" 保存快捷键
map <leader>ss :mksession! my.vim<cr>
" 恢复快捷键
map <leader>rs :source my.vim<cr>

"=== autoformat ===
noremap <C-a> :Autoformat<CR>
inoremap <C-a> <Esc>:Autoformat<CR>
let g:formatdef_harttle = '"astyle --style=1tbs --pad-oper"'
let g:formatters_c = ['harttle']

"=== 颜色配置===
" solarized theme
set t_Co=256  " Explicitly tell vim that the terminal supports 256 colors, need before setting the colorscheme
let g:solarized_termcolors=256
colorscheme solarized
set background=dark
" Transparent background
hi Normal  ctermfg=252 ctermbg=none
set guifont=Menlo:h14

"=== ctrl-s ===
" If the current buffer has never been saved, it will have no name,
" call the file browser to save it, otherwise just save it.
command -nargs=0 -bar Update if &modified 
                           \|    if empty(bufname('%'))
                           \|        browse confirm write
                           \|    else
                           \|        confirm write
                           \|    endif
                           \|endif
nnoremap <silent> <C-S> :<C-u>Update<CR>
inoremap <c-s> <Esc>:Update<CR>

