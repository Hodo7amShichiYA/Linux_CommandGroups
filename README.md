# Linux_CommandGroups

## yum安装:

```
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
yum makecache
```

## PYthon3安装：

```
yum groupinstall "development tools" 

```
## 装一些依赖包

```
yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel expat-devel

```
## 下载python3压缩包 解压 进入目录

```
wget https://www.python.org/ftp/python/3.6.3/Python-3.6.3.tgz
tar -xvf Python-3.6.3.tgz
cd Python-3.6.3

```
## 源码安装 配置--编译--安装

```
./configure --enable-optimizations --prefix=/usr/local/python
make
make install
```
##  创建软连接
```
ln -s /usr/local/python/bin/python3.6 /usr/bin/python3
ln -s /usr/local/python/bin/pip3 /usr/bin/pip3
```
## 修改profile文件:
```
vim /etc/profile
export PATH="/usr/local/python/bin:$PATH"	#(注意:等号两边都不能有任何的空格)
```
## 保存，退出，然后运行：
```
source /etc/profile
```

