## 1. 开发基础环境

1. VS 2013 Community（主要是需要 C/C++运行时库和程序构建工具链，如 msbuild、nmake 等）
2. CMake（源码编译安装或安装程序直接安装）


## 2. Qt for VS

根据需要下载离线安装程序，安装略


## 3. Python

### 在线下载安装包

在线计算机上安装好 python（及 pip），然后下载安装包，注意**与 Python 版本的匹配**

需要的包可以参考 [Ubuntu下Python安装](ubuntu.md#3-python)，但是 Windows 的安装包有的需要从 [Unofficial Windows Binaries for Python Extension Packages](http://www.lfd.uci.edu/~gohlke/pythonlibs/) 下载，有的需要从 [PyPi](https://pypi.python.org/pypi) 或其国内镜像下载

- 下载 [Python安装程序](https://www.python.org/downloads/) ，如果操作系统是 64bit 的就一定下载 64bit 版本的 Python，下载后安装和配置路径，然后再通过 pip download 进行包下载

- 从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/)下载 python 包
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple pip setuptools
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple pep8 pep257 autopep8
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple ipython six pyparsing python-dateutil cycler pytz
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple arrow click
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple functools32
	- pip download -i https://pypi.tuna.tsinghua.edu.cn/simple Sphinx 	# 非常大,不编译文档的话可不安装

- 从 [Unofficial Windows Binaries for Python Extension Packages](http://www.lfd.uci.edu/~gohlke/pythonlibs/) 下载 Windows 平台的 whl 文件包，记得同时把其依赖一并下载下来
	- numpy
	- scipy
	- matplotlib
	- pyqt4 / pyqt5

- 下载 boost 源码


### 离线安装

拷贝在线下载的包，然后在离线计算机上安装

- 首先安装 python
- 针对下载的 whl 文件采用 pip install 安装（略，根据依赖关系注意先后顺序）
- boost 源码安装（可选）
	- `> b2 stage toolset=msvc-12.0 variant=release link=shared threading=multi runtime-link=shared address-model=64 install`


## 4. 其他（可选）

1. [Nuget](https://www.nuget.org/)
