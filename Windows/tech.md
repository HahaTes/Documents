# 1.Windows下gvim显示中文乱码
编辑安装目录下的_vimrc，添加以下代码：
```
set encoding=utf-8
set termencoding=utf-8
set fileencoding=utf-8
set fileencodings=ucs-bom,utf-8,cp936,gb18030
set imcmdline

source $VIMRUNTIME/vimrc_example.vim
source $VIMRUNTIME/mswin.vim
```