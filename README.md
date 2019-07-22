# 搭建Shadowsocks服务器教程

## 第一步:一键安装Shadowsocks

```
wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh && chmod +x shadowsocks.sh && ./shadowsocks.sh 2>&1 | tee shadowsocks.log


```

- 安装过程中分别要输入密码,端口号,和选择加密方式
- 端口建议大于9000,防止与其他软件冲突



## 第二步:一键安装并启动obfs加速

```
cd /usr/src;sudo yum install gcc autoconf libtool automake make zlib-devel openssl-devel asciidoc xmlto;git clone https://github.com/shadowsocks/simple-obfs.git;cd simple-obfs;git submodule update --init --recursive;./autogen.sh;./configure --disable-documentation;make && make install
```



## 第三步:安装BBR加速

```
cd /usr/src && wget -N --no-check-certificate "https://raw.githubusercontent.com/chiakge/Linux-NetSpeed/master/tcp.sh" && chmod +x tcp.sh && ./tcp.sh
```

- 在弹出的界面选择1(安装BBR魔改版内核),安装完成后会提示重启,输入Y重启



## 第四步:启动BBR加速

```
cd /usr/src && ./tcp.sh
```

- 在弹出界面选择使用BBR魔改版内核加速.



## 恭喜,到这一步你就安装完成了.

- 