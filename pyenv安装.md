## 安装pyenv

1. 安装git  `yum -y install git`
* 安装pyenv `curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash`
* 配置环境变量， 在 `~/.bash_profile`里增加如下内容

  ```bash
  export PATH="~/.pyenv/bin:$PATH"
  eval "$(pyenv init -)"
  eval "$(pyenv virtualenv-init -)"
  ```
## 安装Python

### centos

1. 安装编译工具 `yum -y install gcc make patch`
* 安装依赖 `yum -y install gdbm-devel openssl-devel sqlite-devel readline-devel zlib-devel bzip2-devel`
* 安装Python 3.5.2 `pyenv install 3.5.2`

### ubuntu

1. 安装编译工具 `apt-get -y install gcc make patch`
* 安装依赖 `apt-get -y install libgdbm-dev libssl-dev libsqlite-dev libreadline-dev zlib1g-dev libbz2-dev`
* 安装Python 3.5.2 `pyenv install 3.5.2`

## 使用pyenv

### local命令
local命令切换当前目录及其子目录的Python版本， 可以通过删除 `.python-version`恢复默认Python版本

### global命令
global名切换全局默认Python版本

**永远不要使用global命令**

### virtualenv命令
创建虚拟环境 `pyenv virtualenv $bash_version $name`

### uninstall命令
卸载某个版本， 包括虚拟环境
