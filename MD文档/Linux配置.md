# Linux 安装nginx

#### 安装nginx

下载Nginx安装包：

1. 官网：http://nginx.org/en/download.html
2. linux执行命令：`wget http://nginx.org/download/nginx-1.22.0.tar.gz`

##### 安装步骤

```
# 安装依赖
yum -y install gcc zlib zlib-devel pcre-devel openssl openssl-devel
# 解压缩
tar -zxvf nginx-1.22.0.tar.gz
cd nginx-1.22.0
# 执行配置
./configure
# 编译安装(默认安装在/usr/local/nginx)
make
make install
```

##### 启动： 进入Nginx/sbin 目录 `./nginx`

##### 重启： 进入Nginx/sbin 目录 `./nginx -s reload`

#### 防火墙配置

##### 查看防火墙状态：systemctl status firewalld

出现Active: active (running)切高亮显示则表示是启动状态。

出现 Active: inactive (dead)灰色表示停止，看单词也行。

##### 查看开放的端口：firewall-cmd --list-all

##### 设置开放的端口号：sudo firewall-cmd --add-port=8080/tcp --permanent

##### 重启防火墙：firewall-cmd --reload



#### 常见报错

make: *** 没有规则可以创建“default”需要的目标“build”。 停止。

- 这是因为安装nginx 编译时缺少一些依赖造成的
- 安装依赖
- yum -y install gcc openssl openssl-devel pcre-devel zlib zlib-devel
- 再重新执行上一步





