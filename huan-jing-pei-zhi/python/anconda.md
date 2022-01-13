---
description: Anaconda（开源的Python发行版本）
---

# Anconda

_Anaconda (开源的Python包管理器)是一个python发行版，包含了conda、Python等180多个科学包及其依赖项。 包含了大量的包，使用anaconda无需再去额外安装所需包。_

## Install and Configure

### Linux安装

**1、Anaconda安装包下载**

（1）[官网下载](https://www.anaconda.com/products/individual#download-section)，下载速度较慢 

（2）[清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/)

最新的Anaconda清华镜像下载：

```bash
wegt https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/Anaconda3-5.3.1-Linux-x86_64.sh
```

**2、安装Anaconda**

（1）进入文件下载目录

```bash
cd ~/software
```

（2）运行安装包

```bash
bash Anaconda3-5.3.1-Linux-x86_64.sh
```

（3）回车键，进入注册信息页面 

（4）按q跳过阅读，yes 

（5）默认安装在用户目录下，直接回车即可安装；若想自定义安装目录，直接输入安装目录，回车即可。 

（6）Do you wish the installer to initialize Anaconda3 by running conda init ? 输入 no，回车

（7）安装完毕

**3、修改环境变量**

- 将Anaconda添加到用户环境变量中

```bash
vim ~/.bashrc
```

- 按 i 键插入编辑，在文件底部添加下面内容

```bash
# 在.bashrc文件底部添加  
# 为了避免与其他服务器用户产生命令冲突,使用自己的英文名+Python替代python 
alias myPython='/root/anaconda3/bin/python'   
# 这里写anaconda的安装路径
export PATH='/root/anaconda3/bin:$PATH'
```

- 修改完毕，按ESC键退出编辑模式，输入“:wq”保存退出

- source一下

```bash
source ~/.bashrc
```

**4、检查是否安装成功**

```bash
conda --version
```

**5、创建anaconda虚拟环境**

这里我们用 Anaconda 的命令来创建虚拟环境。使用 `conda create -n your_env_name python=X.X`，使用该命令创建 python 版本为 X.X，名字为 your_env_name 的虚拟环境。your_env_name 文件可以在 Anaconda 安装目录 envs 文件下找到。

```bash
#创建虚拟环境
conda create -n your_env_name python=X.X（3.6、3.7等）

#激活虚拟环境
source activate your_env_name(虚拟环境名称)

#退出虚拟环境
source deactivate your_env_name(虚拟环境名称)

#删除虚拟环境
conda remove -n your_env_name(虚拟环境名称) --all
conda remove --name your_env_name package_name  # 删除环境中的某个包
#查看安装了哪些包
conda list

#安装包
conda install package_name(包名)
conda install scrapy==1.3 # 安装指定版本的包
conda install -n 环境名 包名 # 在conda指定的某个环境中安装包

#查看当前存在哪些虚拟环境
conda env list 
#或 
conda info -e
#或
conda info --envs
#检查更新当前conda
conda update conda
#更新anaconda
conda update anaconda
#更新所有库
conda update --all
#更新python
conda update python
#安装requirements.txt依赖
pip install -r requirements.txt
```

**6、修改anaconda的源，变为国内源**

- 添加清华镜像：

```bash
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
conda config --add https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
```

- 设置搜索时显示通道地址

```bash
conda config --set show_channel_urls yes
```

- 显示添加的源

```bash
conda config --show channels
```

- 删除指定源

```bash
conda config --remove channels
```

- 修改源的配置文件是`~/.condarc`

**7、配置pip镜像源**

```bash
mkdir ~/.pip
cd ~/.pip
vim pip.conf
```

添加内容：

```bash
[global]  
index-url = https://mirrors.aliyun.com/pypi/simple/
```

