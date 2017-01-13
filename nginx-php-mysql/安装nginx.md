# 环境
	Ubuntu 14.04 64位

##安装nginx

### 下载nginx
wget https://nginx.org/download/nginx-1.10.2.tar.gz

### 安装PCRE包(用于rewrite)
sudo apt-get install libpcre3 libpcre3-dev

### 安装zlib--用户gzip
sudo apt-get install zlib1g-dev

## 安装mysql

### 下载mysql最新配置文件
wget https://dev.mysql.com/get/mysql-apt-config_0.8.1-1_all.deb

dpkg -i mysql-apt-config_0.8.1-1_all.deb

apt-get update

apt-get install mysql-server


## 安装 php7

> php7 去除了--with-mysql

### 下载php 
wget http://cn2.php.net/distributions/php-7.1.0.tar.gz

./configure --with-config-file-path=/etc --enable-fpm  --enable-opcache --enable-zip --with-openssl --with-gd --with-mhash --with-mysqli=mysqlnd --with-pdo-mysql=mysqlnd --enable-mbstring --enable-mysqlnd

### 安装libxml2
sudo apt-get install libxml2
sudo apt-get install libxml2-dev

### php7 cannot find openssl's libraries
#### 安装pkg-config
apt-get install pkg-config

### configure: error: png.h not found.
sudo apt-get install libpng-dev