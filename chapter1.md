# 环境准备

- OS: CentOS7
    
    如果CentOS系统版本低于6.7，更新系统库 `yum update`

- 安装依赖库
    
    `yum install autoconf autoconf autoconf-archive automake ncurses-devel curl-devel erlang-asn1 erlang-erts erlang-eunit erlang-os_mon erlang-xmerl help2man js-devel libicu-devel libtool perl-Test-Harness openssl-devel unixODBC-devel`

- 升级Python支版本
    
# 安装Erlang

1. 下载Erlang库
    ```
    # wget http://erlang.org/download/otp_src_R15B01.tar.gz 
    ```

    - 下载地址：http://www.erlang.org/download/otp_src_R15B01.tar.gz
    - 版本需要在R15B01以上
    
2. 解压安装：
    ```shell
    # tar -xvf otp_src_R14B01.tar.gz
    # cd otp_src_R14B01
    # ./configure
    # make && make install
    ```
    
    
