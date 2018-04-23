****

## 目录

* [Windows下gvim显示中文乱码](#windows下gvim显示中文乱码)
* [Scrapy以utf-8编码输出csv时中文乱码](#scrapy以utf-8编码输出csv时中文乱码)
* [找回隐藏的Chrome扩展](#找回隐藏的chrome扩展)
* [桌面右键加入切换电源计划](#4.桌面右键加入切换电源计划)
* [Excel里面快速提取所需信息](#5.Excel里面快速提取所需信息)
* [Win10 设置背景护眼色](#6.Win10设置背景护眼色)
* [tensorflow GPU安装](#7.tensorflow-GPU安装)
* [jupyter配置](#8.jupyter配置)
* [scrapy安装](#9.scrapy安装)



### Windows下gvim显示中文乱码
------
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

Scrapy以utf-8编码输出csv时中文乱码
------

将文件用notepad++打开，将编码 *utf-8无BOM* 改为 *utf-8*, 同时可以将 \n 与 \r 替换，去除多余的空行

找回隐藏的Chrome扩展
------
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

# 5.Excel里面快速提取所需信息
  对于从一系列信息中提取某部分，只需在右边一列第一个单元格输入 提取后的信息，例如从`1234856465ghux456`提取英文，只需在右侧一列输入`ghux`，然后按`Ctrl + E` 即可。
# 6.Win10设置背景护眼色
  新建bat文件，输入
  ```bat
reg add "HKCU\Control Panel\Colors" /v Window /t REG_SZ /d "202 234 206" /f
  ```
  运行即可。恢复时只需将颜色数字改为 `255 255 255` 。


# 7.tensorflow-GPU安装

首先安装官网推荐的版本（十分重要，新版本可能不支持），在anaconda创建新的Python3.5环境，首先卸载自带的setuptools，使用官方源安装。
```pip
pip uninstall setuptools
pip install setuptools
pip install tensorflow-gpu
在官方源安装常用包
pip install pandas matplotlib sklearn scipy
pip install jupyter notebook spyder
```
之后安装TensorFlow版本


# 8.jupyter配置

在anaconda promot里面激活对应环境后（activate xx),输入`jupyter notebook --generate-config`,在配置文件里面修改路径`c.NotebookApp.notebook_dir = u'E:\\Python'`

# 9.scrapy安装

To install this package with conda run:
conda install -c conda-forge scrapy