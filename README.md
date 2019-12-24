# Linux_CommandGroups
---------

yum安装:
```
1、备份
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
2、下载新的CentOS-Base.repo 到/etc/yum.repos.d/
CentOS 5

wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-5.repo
或者

curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-5.repo
CentOS 6

wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
或者

curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
CentOS 7

wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
或者

curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
3、之后运行yum makecache生成缓存
生成缓存

yum makecache

```

PYthon3安装：
```
安装开发工具包

# 安装开发工具
yum groupinstall "development tools" 
# 装一些依赖包
yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel expat-devel
下载python3压缩包

# https://www.python.org/downloads/release/python-363/ 有下载地址
wget https://www.python.org/ftp/python/3.6.3/Python-3.6.3.tgz
# 或者在windnows下下载好，拉到linux中
解压

#
tar -xvf Python-3.6.3.tgz
# 进入到目录
cd Python-3.6.3
源码安装 三步走

# 配置
./configure --enable-optimizations --prefix=/usr/local/python
# 编译
make
#安装
make install
# 可以合成一步 make && make install
如何执行python3

# 第一种方式 创建软连接
ln -s /usr/local/python/bin/python3.6 /usr/bin/python3
ln -s /usr/local/python/bin/pip3 /usr/bin/pip3

# 设置成 /usr/local/python/bin 设置成环境变量
#通过修改profile文件:
vim /etc/profile
export PATH="/usr/local/python/bin:$PATH"	#(注意:等号两边都不能有任何的空格)
保存，退出，然后运行：
source /etc/profile
#即可生效
```
