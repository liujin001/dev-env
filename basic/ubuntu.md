## 1. 开发基础环境

**Ubuntu 16 采用 `apt` 取代 `apt-get`, `apt-search` 等, 但 `apt-get` 也可以继续使用**


```shell
$ sudo apt-get install build-essential libtool autoconf automake m4 perl
$ sudo apt-get install git git-gui gitk git-flow tree cloc

$ sudo apt-get install uuid-dev pkg-config vim vim-runtime doxygen graphviz
$ sudo apt-get install default-jre python3-dev python3-doc python3-venv zlib1g-dev

$ sudo apt-get install default-jdk
# $ sudo apt-get install default-jre

$ sudo apt-get install mysql-server mysql-client libmysqlclient-dev
# 安装完成后，修改 /etc/mysql/my.cnf 文件来配置mysql数据库
# $ sudo apt-get install mysql-workbench

$ sudo apt-get install cmake cmake-data cmake-doc
# 不安装 cmake-gui , 太大而且需要安装 Qt 4 依赖
# 如果需要 cmake-gui, 则先安装 Qt 然后直接基于已有的 Qt 采用源码编译 cmake

$ sudo apt-get install libx11-dev libpng-dev libgif-dev libjpeg9-dev libfreetype6-dev libxslt-dev

# $ sudo apt-get install libdbus-1-dev libgl1-mesa-dev freeglut3-dev
# dbus, opengl, for Qt 5.x, Qt 5.x本还需要ssl，暂时没用所以没安装
$ sudo apt-get install libgl1-mesa-dev mesa-common-dev

# $ sudo apt-get install libboost1.55-dev libboost1.55-doc libboost-python1.55-dev     # PyTango需要
$ sudo apt-get install libboost-dev libboost-python-dev
# 针对 PyTango ，好像只需要安装 libboost-python-dev 即可

$ sudo apt-get install swig2.0 swig2.0-doc    # 安装 hdb++/hdbextractor 需要

$ apt-get install curl openssh-server ca-certificates postfix

```


## 2. Qt

根据需要下载离线安装程序，安装略


## 3. Python

### 在线下载安装包

在互联网计算机上安装 python 及 pip，然后再通过 pip download 下载安装包

**下面列出的包可能不全**

- 下载 pip：[get-pip.py](https://raw.github.com/pypa/pip/master/contrib/get-pip.py)， [pip-X.X.tar.gz](https://pypi.python.org/packages/source/p/pip)， 把两个都下载下来，任意一个都应该可以把 pip 离线安装上
- 从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/)下载 python 包
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple pip setuptools
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple pep8 pep257 autopep8
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple ipython six pyparsing python-dateutil cycler pytz decorator path.py
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple numpy scipy ply lxml spyder cython Pillow
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple arrow click
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple futures gevent
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple Sphinx 	# 非常大,不编译文档的话可不安装
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple pytango fandango 
- 下载 [sip](https://www.riverbankcomputing.com/software/sip/download)， [pyqt](https://riverbankcomputing.com/software/pyqt/download5) 源码(拟采用源码安装 pyqt)
- 下载 [pytango](https://pypi.python.org/pypi/PyTango/9.2.1) 及 [matplotlib](https://pypi.python.org/pypi/matplotlib/) 源码

### 离线安装

拷贝在线下载的所有包，然后在离线计算机上安装

- 首先安装 pip（选其一） 
	- `$ python get-pip.py`
	- 解压pip-X.X.tar.gz，然后 `$ python setup.py install`
- 采用 pyvenv 建立虚拟环境，然后在虚拟环境中继续安装
- 针对下载的 whl 文件或源码压缩包文件采用 pip install 安装（略，根据依赖关系注意先后顺序）
- 源码安装 sip， pyqt（略，按官方的流程即可）
- 源码安装 matplotlib