![Shadowsocks](https://github.com/teddysun/shadowsocks_install/raw/master/shadowsocks.png)
# Auto install Shadowsocks Server

shadowsocks.sh
===============
- Auto Install Shadowsocks(Python) Server for CentOS/Debian/Ubuntu
- https://teddysun.com/342.html

使用方法：

使用root用户登录，运行以下命令：
```
wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log
```
卸载方法：

使用root用户登录，运行以下命令：
```
./shadowsocks.sh uninstall
```
##

shadowsocks-libev.sh
===============
- Auto Install Shadowsocks(libev) Server for CentOS
- https://teddysun.com/357.html

使用方法：

使用root用户登录，运行以下命令：
```
wget --no-check-certificate -O shadowsocks-libev.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev.sh
chmod +x shadowsocks-libev.sh
./shadowsocks-libev.sh 2>&1 | tee shadowsocks-libev.log
```
卸载方法：

使用 root 用户登录，运行以下命令：
```
./shadowsocks-libev.sh uninstall
```
安装完成后即已后台启动 Shadowsocks-libev ，运行：
```
/etc/init.d/shadowsocks status
```
可以查看进程是否启动。

本脚本安装完成后，会将 Shadowsocks-libev 加入开机自启动。
##

shadowsocks-libev-debian.sh
===============
- Auto Install Shadowsocks(libev) Server for Debian/Ubuntu
- https://teddysun.com/358.html

使用方法：

使用root用户登录，运行以下命令：
```
wget --no-check-certificate -O shadowsocks-libev-debian.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev-debian.sh
chmod +x shadowsocks-libev-debian.sh
./shadowsocks-libev-debian.sh 2>&1 | tee shadowsocks-libev-debian.log
```
卸载方法：

使用 root 用户登录，运行以下命令：
```
./shadowsocks-libev-debian.sh uninstall
```
本脚本安装完成后，已将 Shadowsocks-libev 加入开机自启动

##

shadowsocks-go.sh
===============
- Auto Install Shadowsocks(Go) Server for CentOS/Debian/Ubuntu
- https://teddysun.com/392.html

使用方法：

使用root用户登录，运行以下命令：
```
wget --no-check-certificate -O shadowsocks-go.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-go.sh
chmod +x shadowsocks-go.sh
./shadowsocks-go.sh 2>&1 | tee shadowsocks-go.log
```
卸载方法：

使用 root 用户登录，运行以下命令：
```
./shadowsocks-go.sh uninstall
```
安装完成后即已后台启动 Shadowsocks-go ，运行：
```
/etc/init.d/shadowsocks status
```
可以查看 Shadowsocks-go 进程是否已经启动。

本脚本安装完成后，已将 shadowsocks-go 加入开机自启动。

##

shadowsocks-crond.sh
===============
- Check Shadowsocks(All version) Server is running or not, and start it if not running
- https://teddysun.com/525.html

一、下载安装

首先需要将脚本下载到某个固定路径下，比如 /opt 下，再赋予执行权限。

执行以下命令：
```
wget --no-check-certificate -O /opt/shadowsocks-crond.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-crond.sh
chmod 755 /opt/shadowsocks-crond.sh
```
二、检查 cron 进程

执行以下命令，检查 cron 进程是否存在：
```
ps -ef | grep -v grep | grep cron
```

如果存在返回值，则表示 cron 已经正确安装并处于启动中。

否则，则需要安装 cron。

CentOS/Redhat/Amazon 执行如下命令：
```
yum install -y crontabs
```

Debian/Ubuntu 执行如下命令：
```
apt-get install -y cron
```
三、配置 cron 计划

假设监视脚本路径就是 /opt/shadowsocks-crond.sh

假设设为每 5 分钟监视一次。

那么配置 cron 计划如下：
```
(crontab -l ; echo "*/5 * * * * /opt/shadowsocks-crond.sh") | crontab -
```
以上表示，在保留原有的 cron 设置的前提下，追加设置

*/5 * * * * /opt/shadowsocks-crond.sh

即每过 5 分钟，执行一次脚本 /opt/shadowsocks-crond.sh

这样系统便会每 5 分钟检查一下 Shadowsocks 进程是否存在，如果不存在了会自动重新启动。

脚本每次运行会写日志的，日志完整路径如下：

/var/log/shadowsocks-crond.log

##

shadowsocksR.sh
===============
- Auto Install ShadowsocksR Server for CentOS/Debian/Ubuntu
- https://shadowsocks.be/9.html

使用方法：

使用root用户登录，运行以下命令：
```
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocksR.sh
chmod +x shadowsocksR.sh
./shadowsocksR.sh 2>&1 | tee shadowsocksR.log
```
卸载方法：

使用 root 用户登录，运行以下命令：
```
./shadowsocksR.sh uninstall
```
安装完成后即已后台启动 ShadowsocksR ，运行：
```
/etc/init.d/shadowsocks status
```
可以查看 ShadowsocksR 进程是否已经启动。

本脚本安装完成后，已将 ShadowsocksR 自动加入开机自启动。

##

shadowsocks-all.sh
==================
- Auto Install Shadowsocks Server (all version) for CentOS/Debian/Ubuntu
- https://teddysun.com/486.html

使用方法

使用root用户登录，运行以下命令：
```
wget --no-check-certificate -O shadowsocks-all.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-all.sh
chmod +x shadowsocks-all.sh
./shadowsocks-all.sh 2>&1 | tee shadowsocks-all.log
```
卸载方法

若已安装多个版本，则卸载时也需多次运行（每次卸载一种）

使用root用户登录，运行以下命令：
```
./shadowsocks-all.sh uninstall
```
启动脚本

启动脚本后面的参数含义，从左至右依次为：启动，停止，重启，查看状态。
```
Shadowsocks-Python 版：

/etc/init.d/shadowsocks-python start | stop | restart | status

ShadowsocksR 版：

/etc/init.d/shadowsocks-r start | stop | restart | status

Shadowsocks-Go 版：

/etc/init.d/shadowsocks-go start | stop | restart | status

Shadowsocks-libev 版：

/etc/init.d/shadowsocks-libev start | stop | restart | status
```
##

haproxy.sh
===============
- Auto Install haproxy for Shadowsocks Server
- https://shadowsocks.be/10.html

使用方法：

使用root用户登录，运行以下命令：
```
wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/haproxy.sh
chmod +x haproxy.sh
./haproxy.sh
```
第一步输入需要 haproxy 代理的端口号，这里要跟 Shadowsocks 服务器开放的端口号一致。

第二步输入 Shadowsocks 公网 IPv4（注意：不是 haproxy 本机的 IP 地址）

卸载方法：

使用 root 用户登录，Debian 或 Ubuntu 系统运行以下命令：
```
apt-get -y remove haproxy
```
CentOS 系统运行如下命令：
```
yum -y remove haproxy
```
然后再删除 haproxy 的配置文件目录即可，命令如下：
```
rm -rf /etc/haproxy
```
使用命令：

启动：```service haproxy start```

停止：```service haproxy stop```

重启：```service haproxy restart```

状态：```service haproxy status```

配置文件路径：/etc/haproxy/haproxy.cfg

##

Copyright (C) 2014-2018 Teddysun
