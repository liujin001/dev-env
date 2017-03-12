## 1. 开发基础环境

**针对 RHEL/CentOS，需要 [EPEL](http://www.tecmint.com/how-to-enable-epel-repository-for-rhel-centos-6-5/)**

```shell
$ sudo yum install epel-release
$ sudo yum install gcc gcc-c++ kernel-devel libstdc++-devel
$ sudo yum install automake autoconf libtool m4 make tree cloc
$ sudo yum install zlib-devel bzip2-devel openssl-devel
$ sudo yum install uuid-devel doxygen graphviz patch subversion git git-gui gitk gitflow
$ sudo yum install dbus-devel
# CentOS 7 自带的 cmake 版本太低, 所以不采用包安装 cmake, 直接源码编译安装
$ sudo yum install ncurses-devel libcurl-devel    # 编译 cmake 需要

$ sudo yum install libpng-devel giflib-devel openjpeg-devel freetype-devel

$ sudo yum install boost-devel boost-python 	# 不需要 mpi 版本
# 要 build PyTango，必须把 boost 和 boost-python 都要安装上！！！
# 如果需要采用 python 3.x 来安装 PyTango，必须自己编译安装 boost, boost_python
$ sudo yum install libquadmath-devel	# build boost 需要

$ sudo yum install mesa-libGL-devel      # OpenGL库安装， Qt 开发准备
# $ sudo yum install java-1.8.0-openjdk-devel   # 安装 JDK(先查询最新版本)

$ sudo yum install swig swig-doc          # 安装 hdb++/hdbextractor 需要
$ sudo yum install libjpeg-turbo-devel    # 安装 MathGL 时需要这个 jpeg 库，而不是 openjpeg

$ yum list | grep python3 	# 查询一下最新的 Python3 版本，选择安装版本
$ sudo yum install python34-devel python34-tkinter python34-tools
# 上面的包安装后，pyvenv 也安装好了:  $ pyvenv -h

# MySQL：
# $ wget http://repo.mysql.com/mysql57-community-release-el7-7.noarch.rpm
# $ sudo rpm -ivh mysql57-community-release-el7-7.noarch.rpm
# $ ls -l /etc/yum.repos.d/mysql-community*
# $ sudo yum install mysql-server mysql mysql-devel
# $ service mysqld start

$ sudo yum install curl policycoreutils openssh-server openssh-clients postfix

```


## 2. Qt

根据需要下载离线安装程序，安装略


## 3. Python

参见 [Ubuntu下Python安装](ubuntu.md#3-python)

在 CentOS 7 下采用 pyvenv-3.4 建立虚拟环境有一个 bug，出现不能建立一个“含 pip 的虚拟环境”的现象，对于 pyvenv-3.5 或 3.6 不知道是否还有这个 bug，如果出现这个 bug，解决思路就是：先创建一个不含 pip 的虚拟环境，然后手动安装 pip ：

```shell
$ pyvenv-3.4 --without-pip venvdir
$ source venvdir/bin/activate
# 手动安装 pip，然后再安装其他包
```