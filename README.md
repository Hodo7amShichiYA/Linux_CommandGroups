# Linux_CommandGroups
## 基本操作:
### 修改宝塔端口:
```
echo '123456' > /www/server/panel/data/port.pl && service bt restart
```
### centos7关闭端口:
```
firewall-cmd --permanent --zone=public --remove-port=123456/tcp
```
### centos7放行端口:
```
firewall-cmd --zone=public --add-port=123456/tcp --permanent 
```
### centos7防火墙重载:
```
systemctl reload firewalld
```

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
wget https://www.python.org/ftp/python/3.7.6/Python-3.7.6.tgz
tar -xvf Python-3.7.6.tgz
cd Python-3.7.6
./configure --enable-optimizations --prefix=/usr/local/python
make
make install
ln -s /usr/local/python/bin/python3.7 /usr/bin/python3
ln -s /usr/local/python/bin/pip3 /usr/bin/pip3
vim /etc/profile
export PATH="/usr/local/python/bin:$PATH"	#(注意:等号两边都不能有任何的空格)
source /etc/profile
```
## virtualenv 使用
```
pip3 install virtualenv
virtualenv –p /usr/local/python/bin/python3.7 [虚拟环境名]

#进入和退出
source /root/[环境名]/bin/activate
deactivate
```

## 安装Youtube-dl
```
wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl
chmod a+rx /usr/local/bin/youtube-dl
```

## 安装 FFmpeg
```
#安装 yasm
wget http://www.tortall.net/projects/yasm/releases/yasm-1.3.0.tar.gz
tar -zxvf yasm-1.3.0.tar.gz
cd yasm-1.3.0
./configure
make
make install

#安装 FFmpeg
cd /root
wget http://www.ffmpeg.org/releases/ffmpeg-3.3.3.tar.gz
tar -zxvf ffmpeg-3.3.3.tar.gz
cd ffmpeg-3.3.3
./configure
make
make install
```
## 安装 V2R
```
yum -y install wget
wget https://install.direct/go.sh
yum install -y zip unzip  
bash go.sh
```
## 控制
```
systemctl start v2ray
systemctl stop v2ray
systemctl restart v2ray

systemctl enable v2ray #开机启动
```
## 配置
/etc/v2ray/config.json
```
{
  "inbounds": [
    {
      "port": 1024, // 监听端口
      "protocol": "shadowsocks",
      "settings": {
        "method": "aes-128-gcm",
        "ota": true, // 是否开启 OTA
        "password": "sspasswd"
      }
    }
  ],
  "outbounds": [
    {
      "protocol": "freedom",  
      "settings": {}
    }
  ]
}

```
