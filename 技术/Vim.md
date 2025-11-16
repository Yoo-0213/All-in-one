---
tags:
  - 工具
---
## 配置代码
```verilog
"-------------------------- general config --------------------------
" 设置softtabstop有一个好处是可以用Backspace键来一次
" 删除4个空格. softtabstop的值为负数,会使用shiftwidth
" 的值,两者保持一致,方便统一缩进.
set softtabstop=-1
set expandtab                                   " tab字符替换成空格
set tabstop=4                                   " 设置tab字符的长度为4
set shiftwidth=4                                " 自动缩进时，缩进长度为4
set nobackup                                    " 不需要备份备份
set noswapfile                                  " 不需要临时交换文件
set backspace=indent,eol,start                  " 正常使用backspace
set nocompatible                                " 不兼容vi
autocmd FileType * setlocal formatoptions-=cro  " 取消自动注释
"autocmd BufNewFile *.v 0r ~/.vim/templates/tempfirverilog.v    " 创建.v文件时，自动调用模板

"-------------------------- display config --------------------------
syntax on                                       " 语法高亮
set number                                      " 显示行号
set cursorline                                  " 突出显示当前行
set guifont=Monospace\ Regular\ 10              " 设置字体
set guioptions-=T                               " 隐藏工具栏
set guioptions-=m                               " 隐藏菜单栏
set guioptions-=r                               " 隐藏右侧滚动条
set guioptions-=R                                
set guioptions-=l                                
set guioptions-=L                                
set guioptions-=b                                
set laststatus=2                                " 总是显示状态行
"set fileencodings=utf-8,cp936,big5,latin1      " 遇到中文乱码时打开

"-------------------------- Key Remapping ---------------------------
"在插入模式下生效，将jk映射成Esc
imap jk <Esc>
"在正常模式下生效，将space映射成:
nmap <space> :
"在正常模式下生效，创建和关闭标签页
"nmap <C-S-t> :tabnew<CR>
"nmap <C-S-w> :tabc<CR>
"通过alt + 数字切换标签页
:nn <M-1> 1gt
:nn <M-2> 2gt
:nn <M-3> 3gt
:nn <M-4> 4gt
:nn <M-5> 5gt
:nn <M-6> 6gt
:nn <M-7> 7gt
:nn <M-8> 8gt
:nn <M-9> 9gt
:nn <M-0> :tablast<CR>

"自定义缩写文件导入
if filereadable(expand('E:/Github/Vim/abbreviation.vim'))
    source E:/Github/Vim/abbreviation.vim
endif


"-------------------------- plugin config ---------------------------
"NERDTree
    "F3打开/关闭文件浏览器
    nmap <F3> :NERDTreeToggle <CR>
"EasyAlign
    xmap ga <Plug>(EasyAlign)
    nmap ga <Plug>(EasyAlign)
"neocomplcache
    let g:neocomplcache_enable_at_startup = 1
"nerdcommenter
    au FileType c,cpp setlocal comments-=:// comments+=f://
"gruvbox
    let g:gruvbox_contrast_dark = 'medium'                      " 设置对比度为中
    autocmd vimenter * nested colorscheme gruvbox
    set bg=dark
"automatic
    "\ati进行例化
    map \ati :call g:AutoInst(0)<Esc>
    let g:atu_autoinst_keep_chg   = 1                           " 修改过的连线保留不刷新
    let g:atv_autoinst_incl_width = 0                           " 不添加多bit位宽
    let g:atv_autoinst_incl_cmnt  = 0                           " 不添加//注释
    "对齐位置
    let g:atv_autopara_st_pos     = 4                           " 起始位置
    let g:atv_autopara_name_pos   = 64                          " 信号名对齐位置
    let g:atv_autopara_sym_pos    = 128                         " 第二个括号对齐位置
    let g:atv_autoinst_st_pos     = 4   
    let g:atv_autoinst_name_pos   = 64  
    let g:atv_autoinst_sym_pos    = 128 
"ALE
    let g:ale_set_highting = 0
    let g:ale_log_to_file = 0
    let g:ale_cache_executable_check_failures=1

"----------------------------- plugin -------------------------------
"更改插件存放路径即可
call plug#begin()
Plug 'E:/Github/Vim/vim_plugin/vim-startify-master'
Plug 'E:/Github/Vim/vim_plugin/vim-easy-align-master'
Plug 'E:/Github/Vim/vim_plugin/vim-airline-master'
Plug 'E:/Github/Vim/vim_plugin/nerdtree-master'
Plug 'E:/Github/Vim/vim_plugin/nerdcommenter-master'
Plug 'E:/Github/Vim/vim_plugin/neocomplcache.vim-master'
Plug 'E:/Github/Vim/vim_plugin/gruvbox-master'
Plug 'E:/Github/Vim/vim_plugin/automatic-verilog-master'
Plug 'E:/Github/Vim/vim_plugin/ale-master'
call plug#end()
```

---
## 配置方法
### windows
1. 找到vim的配置文件路径 `F:/Vim/_vimrc`，修改为上面的代码，并保存
2. 将 `Vim\\vim_plugin` 复制到vim的安装路径下，并把其中的 `plug.vim` 复制到 `vim\vim91\autoload` 中
3. 配置完成
### Linux
1. 找到vim的配置文件路径 `~/.vimrc`，修改为上面代码，并保存
2. 将 `Vim\vim_plugin` 复制到vim的安装路径下，并把其中的 `plug.vim` 复制到 `~/.vim/autoload` 中
3. 配置完成

## 插件列表
|**插件名称**|**功能**|**github链接**|
|---|---|---|
|vim-plug|插件管理|https://github.com/junegunn/vim-plug|
|NERDTree|文件浏览器|https://github.com/preservim/nerdtree|
|gruvbox|主题配色|https://github.com/morhetz/gruvbox|
|nerdcommenter|注释工具|https://github.com/preservim/nerdcommenter|
|neocomplcache|代码补全|https://github.com/Shougo/neocomplcache.vim|
|vim-airline|状态栏美化|https://github.com/vim-airline/vim-airline|
|vim-easy-align|代码对齐|https://github.com/junegunn/vim-easy-align|
|automatic-verilog|自动例化|https://github.com/HonkW93/automatic-verilog|
|ALE|语法检查工具|https://github.com/dense-analysis/ale|
|vim-startify|最近打开文件|https://github.com/mhinz/vim-startify|
|vtags|信号追踪|https://www.vim.org/scripts/script.php?script_id=5494|

### NERDTree
```Verilog
"配置代码
    "F3打开/关闭文件浏览器
    nmap <F3> :NERDTreeToggle <CR>
    "NERDTree配置  
	let NERDChristmasTree=1 "显示增强
	let NERDTreeAutoCenter=1 "自动调整焦点
	let NERDTreeShowFiles=1 "显示文件
	let NERDTreeShowLineNumbers=1 "显示行号
	let NERDTreeHightCursorline=1 "高亮当前文件
	let NERDTreeShowHidden=0 "显示隐藏文件
	let NERDTreeMinimalUI=0 "不显示'Bookmarks' label 'Press ? for help'
	let NERDTreeWinSize=31 "窗口宽度
```

| **按键**             | **说明**                        |
| ------------------ | ----------------------------- |
| Ctrl + w + j/k/h/l | 切换左/右/上/下边视窗                  |
| o                  | 打开文件、目录                       |
| i                  | 拆分出窗口打开所选文件（水平视窗）             |
| s                  | 拆分出窗口打开所选文件（垂直视窗）             |
| R                  | 刷新目录                          |
| t                  | 在标签页中打开                       |
| T                  | 在后台标签页中打开（焦点仍保持在当前标签页）        |
| I                  | 显示隐藏文件                        |
| x                  | 关闭当前文件的父目录                    |
| C                  | 已当前根作为选定目录                    |
| u                  | 将树根上移一个目录                     |
| ma                 | 在需要创建文件的目录下敲命令ma然后输入要创建的文件名   |
| md                 | 选择删除的文件敲命令md输入y然后回车           |
| mm                 | 选择移动或修改的文件敲命令mm然后输入对应的目录和名称回车 |
| ?                  | 快速帮助                          |

---
## 报错
1. 如果显示`'git' executable was found` 就在`设置—系统—关于—高级系统设置—高级—环境变量—path—编辑—新建`添加Git的环境变量
2. 如果看到^M，就设置`:set ff=unix`