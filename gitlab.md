## 1. Gitlab Community

源码编译有点复杂，直接采用包安装

GitLab 不能运行于 Windows 平台，估计也没有支持 Windows 的计划

安装[参见](https://mirrors.tuna.tsinghua.edu.cn/help/gitlab-ce/)

### Ubuntu 16

- 下载脚本备用: `$ curl -O https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh`
- 从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/ubuntu/pool/xenial/main/g/gitlab-ce/)下载最新的 GitLab 的安装文件
- 安装: `$ dpkg -i gitlab-ce_8.x.x-ce.0_amd64.deb`
- 配置（/etc/gitlab/gitlab.rb），关键要配置好地址
	- `external_url '你的公网网址'`


### CentOS 7

- 下载脚本备用: `$ curl -O https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh`
- 从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7/)下载最新的 GitLab 的安装文件
- 安装: `$ $ rpm -i gitlab-ce-XXX.rpm`
- 配置（/etc/gitlab/gitlab.rb），关键要配置好地址
	- `external_url '你的公网网址'`


## 2. Gitlab CI Multi Runner

暂时采用 Gitlab runner，有时间再来尝试 Jenkins

[安装说明](https://mirrors.tuna.tsinghua.edu.cn/help/gitlab-ci-multi-runner/)

gitlab-ci-multi-runner 仅支持 x86-64 架构？？

### Ubuntu 16

- 下载脚本备用: `$ curl -O https://packages.gitlab.com/install/repositories/runner/gitlab-ci-multi-runner/script.deb.sh`
- 从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/gitlab-ci-multi-runner/ubuntu/pool/xenial/main/g/gitlab-ci-multi-runner/)下载最新的 GitLab Runner 安装文件
- 安装: `$ dpkg -i gitlab-ci-multi-runner_1.11.1_amd64.deb`
- 注册 runner: `$ sudo gitlab-ci-multi-runner register`
- 帮助: `$ gitlab-runner help ( $ gitlab-runner <command> --help)`

### CentOS 7

- 下载脚本备用: `$ curl -O https://packages.gitlab.com/install/repositories/runner/gitlab-ci-multi-runner/script.rpm.sh`
- 从[清华镜像](https://mirrors.tuna.tsinghua.edu.cn/gitlab-ci-multi-runner/yum/el7/)下载最新的 GitLab Runner 安装文件
- 安装: `$ rpm -i gitlab-ci-multi-runner-xxx.x86_64.rpm`
- 注册 runner: `$ sudo gitlab-ci-multi-runner register`
- 帮助: `$ gitlab-runner help ( $ gitlab-runner <command> --help)`

### Windows 64bits

- 下载[Gitlab Runner的Windows安装程序](https://gitlab-ci-multi-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-ci-multi-runner-windows-amd64.exe)
- 安装（略）


## 3. Jenkins