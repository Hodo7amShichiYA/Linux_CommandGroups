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
yum install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel expat-devel
wget https://www.python.org/ftp/python/3.6.3/Python-3.6.3.tgz
tar -xvf Python-3.6.3.tgz
cd Python-3.6.3
./configure --enable-optimizations --prefix=/usr/local/python
make
make install
ln -s /usr/local/python/bin/python3.6 /usr/bin/python3
ln -s /usr/local/python/bin/pip3 /usr/bin/pip3
vim /etc/profile
export PATH="/usr/local/python/bin:$PATH"	#(注意:等号两边都不能有任何的空格)
source /etc/profile
```
## virtualenv 使用
```
pip3 install virtualenv
virtualenv –p /usr/local/python/bin/python3.6 [虚拟环境名]

#进入和退出
source /root/[环境名]/bin/activate
deactivate
```
