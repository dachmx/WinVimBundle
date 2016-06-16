filetype off
execute pathogen#infect()
call pathogen#helptags()
set nocompatible
source $VIMRUNTIME/vimrc_example.vim
source $VIMRUNTIME/mswin.vim
behave mswin

set nu


set rtp+=$HOME/vimfiles/bundle/Vundle.vim/
call vundle#begin('$USERPROFILE/vimfiles/bundle/')
" let Vundle manage Vundle
" required! 
Bundle 'gmarik/vundle'

colorscheme Monokai

set encoding=utf-8

" execute pathogen#infect()

set background=dark

nmap <F9> <Esc>:!ctags -R *<CR>
let g:winManagerWindowLayout='NERDTree|TagList,BufExplorer'

""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"设置Taglist
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""
" 这项必须设定，否则出错,配置taglist的ctags路径
let Tlist_Ctags_Cmd = 'D:\ctags58\ctags.exe'

" 不同时显示多个文件的 tag ，只显示当前文件的
let Tlist_Show_One_File=1
 
" 如果 taglist 窗口是最后一个窗口，则退出 vim
let Tlist_Exit_OnlyWindow=1

"让当前不被编辑的文件的方法列表自动折叠起来 
let Tlist_File_Fold_Auto_Close=1

"把taglist窗口放在屏幕的右侧，缺省在左侧 
let Tlist_Use_Right_Window=1 

"显示taglist菜单
 
let Tlist_Show_Menu=1

"启动vim自动打开taglist
"let Tlist_Auto_Open=1

"""""""""""""""""""""""""""""""
"" winManager setting
"""""""""""""""""""""""""""""""

"设置界面分割
"let g:winManagerWindowLayout = "BufExplorer,FileExplorer|TagList"
let g:winManagerWindowLayout = "TagList|FileExplorer,BufExplorer"
 
"设置winmanager的宽度，默认为25
let g:winManagerWidth = 30
 
"定义打开关闭winmanager按键
nmap <silent> <F8> :WMToggle<cr>

set diffexpr=MyDiff()
function MyDiff()
  let opt = '-a --binary '
  if &diffopt =~ 'icase' | let opt = opt . '-i ' | endif
  if &diffopt =~ 'iwhite' | let opt = opt . '-b ' | endif
  let arg1 = v:fname_in
  if arg1 =~ ' ' | let arg1 = '"' . arg1 . '"' | endif
  let arg2 = v:fname_new
  if arg2 =~ ' ' | let arg2 = '"' . arg2 . '"' | endif
  let arg3 = v:fname_out
  if arg3 =~ ' ' | let arg3 = '"' . arg3 . '"' | endif
  if $VIMRUNTIME =~ ' '
    if &sh =~ '\<cmd'
      if empty(&shellxquote)
        let l:shxq_sav = ''
        set shellxquote&
      endif
      let cmd = '"' . $VIMRUNTIME . '\diff"'
    else
      let cmd = substitute($VIMRUNTIME, ' ', '" ', '') . '\diff"'
    endif
  else
    let cmd = $VIMRUNTIME . '\diff'
  endif
  silent execute '!' . cmd . ' ' . opt . arg1 . ' ' . arg2 . ' > ' . arg3
  if exists('l:shxq_sav')
    let &shellxquote=l:shxq_sav
  endif
endfunction

