## 1. SonarQube

检查安装运行的[Requirements](https://docs.sonarqube.org/display/SONAR/Requirements)，特别注意 JRE/JDK，MySQL 最低版本要求

> The only prerequisite for running SonarQube is to have Java (Oracle JRE 8 onwards or OpenJDK 8 onwards) installed on your machine.

Windows 下如果要运行 64 bit 的 SonarQube 服务, 那就必须安装 64bit 的 JRE or JDK

- 从[SonarQube](http://www.sonarqube.org/downloads/)下载 SonarQube（最新版）和 SonarQube Scanner(Command line)，以及 free Plugins (好像 Python, java 等 Plugins 是 free 的)
- 采用 MySQL 数据库，配置 SonarQube 和 SonarQube Scanner，稍微有点复杂

## 2. SonarQube plugins

plugins 主要针对 C/C++ 和 Python

### c++

[SonarQube C++ Community plugin](https://github.com/SonarOpenCommunity/sonar-cxx)

- 下载[sonar-cxx-plugin-0.9.?-SNAPSHOT.jar](https://ci.appveyor.com/project/SonarOpenCommunity/sonar-cxx/branch/master/artifacts)
- 下载后拷贝到 $SONARQUBE_HOME\extensions\plugins 目录

### 其他

根据需要下载其他语言的 plugins，把所有 plugins 文件拷贝到 $SONARQUBE_HOME\extensions\plugins 目录

## 3. CppCheck

CppCheck是一个C/C++代码缺陷静态检查工具. 不同于C/C++编译器及其它分析工具, CppCheck只检查编译器检查不出来的bug, 不检查语法错误

**CppCheck 不能有效识别中文路径**，所以检测的代码文件路径不要有中文

### Linux

- 下载[cppcheck](https://sourceforge.net/projects/cppcheck/files/cppcheck/)源代码
- 下载[pcre](https://sourceforge.net/projects/pcre/files/)源代码
- 先编译安装 pcre，然后再编译安装 cppcheck

### Windows

- 下载[cppcheck](http://cppcheck.sourceforge.net)
- 安装，并配置好 cppcheck 执行程序路径

## 4. unit test

拟采用下面两个工具做 C/C++ 单元测试， 将代码 clone 下来

- [catch](https://github.com/philsquared/Catch)
- [gtest/gmock](https://github.com/ospector/gtest-gbar)

## 5. Coverage

gcovr 是针对 gcc 的单元测试的代码覆盖率展示工具，Visual Studio 好像自带覆盖率分析工具 ?

- 下载[gcovr](https://pypi.python.org/pypi/gcovr/)源码包
- 在Linux下解压 gcovr-3.?.tar.gz 后将 scripts 目录下的 gcovr(这是一个python脚本) 拷贝到 /usr/bin 目录下