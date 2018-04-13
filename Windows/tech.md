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

# 4.桌面右键加入切换电源计划

在`powershell`里面输入`powercfg.exe /L`查看电源计划的`GUID`，填入之后的command的代码
```
Windows Registry Editor Version 5.00

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan]
"Icon"="powercpl.dll"
"MUIVerb"="电源切换计划"
"Position"="Top"
"SubCommands"=""

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan\Shell]

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan\Shell\Balanced]
"MUIVerb"="平衡"
"Icon"="powercpl.dll"

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan\Shell\Balanced\Command]
@="powercfg.exe /S 381b4222-f694-41f0-9685-ff5bb260df2e"

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan\Shell\High Performance]
"MUIVerb"="高性能"
"Icon"="powercpl.dll"

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan\Shell\High Performance\Command]
@="powercfg.exe /S 8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c"

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan\Shell\Power Saver]
"MUIVerb"="节能"
"Icon"="powercpl.dll"

[HKEY_CLASSES_ROOT\DesktopBackground\Shell\Switch Power Plan\Shell\Power Saver\Command]
@="powercfg.exe /S a1841308-3541-4fab-bc81-f71556f20b4a"


```