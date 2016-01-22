# 环境准备

- OS: CentOS7
    
    >如果CentOS系统版本低于6.7，更新系统库 `yum update`

- 安装依赖库
    
    `yum install autoconf autoconf autoconf-archive automake ncurses-devel curl-devel erlang-asn1 erlang-erts erlang-eunit erlang-os_mon erlang-xmerl help2man js-devel libicu-devel libtool perl-Test-Harness openssl-devel unixODBC-devel`

- Python支版本
> Node不支持Python3.0。主要原因在于GYP项目构建工具采用Python完成开发的，这里建议安装Python2.7，以为node-gpy需要Python 2.7才能正常使用。