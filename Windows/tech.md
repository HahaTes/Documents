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

# 2.Scrapy以utf-8编码输出csv时中文乱码
将文件用notepad++打开，将编码 *utf-8无BOM* 改为 *utf-8*, 同时可以将 \n 与 \r 替换，去除多余的空行

# 3.找回隐藏的Chrome扩展
a. 在浏览器地址栏最右边，待鼠标变成左右双向箭头图标的时候向右拖动，隐藏的扩展图标就会出现。 

b. 重新启用该扩展