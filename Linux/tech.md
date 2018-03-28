# 1. Ubuntu 安装 Face-recognition
``` linux
sudo apt-get install libboost-python-dev cmake
pip install scikit-image
pip install dlib

pip install face_recognition

或者尝试
pip install --index https://mirrors.ustc.edu.cn/pypi/web/simple/ face_recognition
```
参考资料[Face-recognition<Ubuntu16.04下的环境搭建>](http://blog.csdn.net/Gpwner/article/details/78894053)

# 2.Ubuntu 安装 scrapy 框架
a. 检查更新
```linux
(sudo) apt-get update && apt-get upgrade -y && apt-get install python3-pip -y
```
b. 安装虚拟环境并创建基于python3的环境
```linux
pip3 install virtualenv
virtualenv -p /usr/bin/python3.6 p3scrapy
```
c.激活虚拟环境并安装相应的库
```linux
source ./p3scrapy/bin/activate
apt-get install python3-lxml
apt-get install build-essential libssl-dev libffi-dev python-dev
pip install scrapy
```
>  取消激活使用`deactivate`,删除环境直接删除对应文件夹


