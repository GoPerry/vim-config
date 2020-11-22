# vim-config


nmap wv     <C-w>v     " 垂直分割当前窗口
nmap wc     <C-w>c     " 关闭当前窗口
nmap ws     <C-w>s     " 水平分割当前窗口

"-------------------------------------------------------------------------------
"  some additional hot keys
"-------------------------------------------------------------------------------
"    F2   -  write file without confirmation
"    F3   -  call file explorer Ex
"    F4   -  show tag under curser in the preview window (tagfile must exist!)
"    F5   -  open quickfix error window
"    F6   -  close quickfix error window
"    F7   -  display previous error
"    F8   -  display next error
"  S-Tab  -  Fast switching between buffers (see below)
"    C-q  -  Leave the editor with Ctrl-q (see below)
"-------------------------------------------------------------------------------
"
map   <silent> <F1>    :A<CR>
map   <silent> <F2>    :write<CR>
map   <silent> <F3>    :Explore<CR>
nmap  <silent> <F4>    :exe ":ptag ".expand("<cword>")<CR>
map   <silent> <F5>    :copen<CR>
map   <silent> <F6>    :cclose<CR>
map   <silent> <F7>    :cp<CR>
map   <silent> <F8>    :cn<CR>
"
imap   <silent> <F1>    :A<CR>
imap  <silent> <F2>    <Esc>:write<CR>
"imap  <silent> <F3>    <Esc>:Explore<CR>
imap  <silent> <F4>    <Esc>:exe ":ptag ".expand("<cword>")<CR>
imap  <silent> <F5>    <Esc>:copen<CR>
imap  <silent> <F6>    <Esc>:cclose<CR>
imap  <silent> <F7>    <Esc>:cp<CR>
imap  <silent> <F8>    <Esc>:cn<CR>


"""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" cscope setting

if has("cscope")
        set csprg=/usr/bin/cscope              "指定用来执行 cscope 的命令
        set csto=1                             "先搜索tags标签文件，再搜索cscope数据库
        set cst                                "使用|:cstag|(:cs find g)，而不是缺省的:tag
        set nocsverb                           "不显示添加数据库是否成功
        " add any database in current directory
        if filereadable("cscope.out")
                cs add cscope.out                   "添加cscope数据库
        endif
        set csverb                             "显示添加成功与否
endif

" <C-@s的按法是先按"Ctrl+@",然后很快再按"s"

" 按下面这种组合键有技巧,按了<C-_>后要马上按下一个键,否则屏幕一闪

" 就回到nomal状态了

nmap <C-@>s :cs find s <C-R>=expand("<cword>")<CR><CR>
nmap <C-@>g :cs find g <C-R>=expand("<cword>")<CR><CR>
nmap <C-@>c :cs find c <C-R>=expand("<cword>")<CR><CR>
nmap <C-@>t :cs find t <C-R>=expand("<cword>")<CR><CR>
nmap <C-@>e :cs find e <C-R>=expand("<cword>")<CR><CR>
nmap <C-@>f :cs find f <C-R>=expand("<cfile>")<CR><CR>
nmap <C-@>i :cs find i ^<C-R>=expand("<cfile>")<CR>$<CR>
nmap <C-@>d :cs find d <C-R>=expand("<cword>")<CR><CR>

""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""


The git is used for recording the vim setting and plugins installed.
