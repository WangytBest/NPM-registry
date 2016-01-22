# 安装CouchDB数据库
# 安装`Erlang库`

> 1. 下载地址：[Erlang下载地址](http://www.erlang.org/download/otp_src_R15B01.tar.gz)
> 2. 版本需要在`R15B01`以上
> 3. 从源码编译安装Erlang,有两个库或工具是必须的：
    - 完整的`GCC编译环境`
    - `Ncurses开发库`


1. 下载`Erlang库`
    ```
    # wget http://erlang.org/download/otp_src_R15B01.tar.gz 
    ```
2. 解压安装
    ```shell
    # yum install gcc glibc-devel make ncurses-devel openssl-devel autoconf -y 
    # tar -xvf otp_src_R14B01.tar.gz
    # cd otp_src_R14B01
    # ./configure
    # make && make install
    ```
3. 添加环境变量
    ```
    # vim /etc/profile
    添加：
    export PATH=$PATH:/usr/local/erlang/bin/
    ```
4. 测试安装
    ```
    # erl
    ```
    
# 安装`MozillaSpidMonkey`

> 1. 下载地址：[MozillaSpidMonkey](http://ftp.mozilla.org/pub/mozilla.org/js/mozjs17.0.0.tar.gz)
> 2. 代码名称：` mozjs17.0.0.tar.gz`

1. 解压安装
```
# tar -xvf mozjs17.0.0.tar.gz
# cd mozjs17.0.0/js/src/
# ./configure
# make && make install
```

# 安装CouchDB数据库
>1. 下载地址：[CouchDB下载](http://mirror.tcpdiag.net/apache/couchdb/source/1.6.1/apache-couchdb-1.6.1.tar.gz)
>2. 代码名称：`mozjs17.0.0.tar.gz`

1. 解压安装
    ```shell
    #wget http://mirrors.advancedhosters.com/apache/couchdb/source/1.6.0/apache-couchdb-1.6.1.tar.gz  
    # tar -xvf apache-couchdb-1.6.1.tar.gz
    # cd apache-couchdb-1.6.0  
    # ./configure
    # make && make install
    ```
2. 测试安装
    ```
    #$ couchdb  
    Apache CouchDB 1.2.0 (LogLevel=info) is starting.  
    Apache CouchDB has started. Time to relax.  
    [info] [<0.32.0>] Apache CouchDB has started on http://127.0.0.1:5984/
    ```

# 配置CouchDB数据库

```shell
# chown -R couchdb:couchdb /usr/local/var/lib/couchdb /usr/local/var/log/couchdb /usr/local/var/run/couchdb
# ln -sf /usr/local/etc/rc.d/couchdb /etc/init.d/couchdb
# chkconfig --add couchdb
# chkconfig couchdb on
```

# 设置IP和端口
```
# vim /usr/local/etc/couchdb/local.ini
[httpd]
port = 5984
bind_address = 192.168.0.128
```

# 启动与停止
>* 启动 ：`# /etc/init.d/couchdb start`
>* 查看状态：`# /etc/init.d/couchdb status`
>* 停止：`#/etc/init.d/couchdb stop`

# 访问数据库
>[浏览器访问](http://127.0.0.1:5984/_utils)：http://127.0.0.1:5984/_utils

# CouchDB添加用户

>1. 打开管理画面：[访问地址](http://127.0.0.1:5984/_utils)( http://127.0.0.1:5984/_utils/)
>2. 点击画面右下角的`Fix this`，创建用户。admin/admin

    

