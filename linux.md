# 基本操作
不会的命令用man来学习.
## 基本命令
1. linux@os:~$     用户名(可以切换)＠主机名:路径+用户权限级别    其中$代表登录的普通用户权限　还有其他权限
2. windows下：目录时属于分区的  不区分大小写
3. linux:只有目录没有分区　　　严格区分大小写　　安装的程序分装在不同的目录下,没有指定的目录
4. 只输入cd就进到主目录
5. mv: 第二个参数存在而且是目录就是剪切；第二个参数不存在就是重命名
6. 目录的拷贝:cp -a/-r　目录
7. 目录的删除:rm -r/-rf(慎用－rf) 目录
8. du -mh 软件名　查看文件大小

## 文件的压缩和解压
### 后缀为.gz　　
**注**:只对文件压缩和解压缩
```sh  
gzip filename
gunzip filename.gz
```
### 后缀为.bz2
**注**:只对文件压缩和解压缩
```sh
bzip2 filename
bunzip2 filename.bz2
```
### tar
压缩:tar 选项　新名　原名

一般常用(对目录的操作)：

１.tar czvf dir.tar.gz dir

注解:c--创建　ｚ--后缀为.tar.gz  v--解压过程可视　　f--指定解压文件

2. tar cjvf dir.tar.bz2 dir

注解:j--后缀为.tar.bz2

3. tar cJvf dir.tar.xz dir

解压: tar xvf dir.tar.后缀名

## ubuntu下的Deb软件包的基本操作(二进制软件包－－sudo加权限)

1.　组成:软件包名_版本号和修订版本号_运行机器的平台架构.deb

例:sl_3.03-17_amd64.Deb

2.　本地deb包的操作命令dpkg

    1. 安装:dpkg -i sl_3.03-17_amd64.deb
    2. 软件包卸载 dpkg -r sl
    3. 软件包彻底卸载，移除所有配置文件 dpkg -P sl
    4. 查看软件包的安装状态 dpkg -s sl
    5. 查看软件包的安装路径 dpkg -L sl
    
    注:用于本地deb软件包的安装、卸载和查询软件包相关的信息，操作方便快捷，但是如果安装的软件包和其他软件包之间具有依赖关系，那么本地软件包
    管理不能很好的解决这种依赖问题。
    
3. 在线管理操作命令apt

    1. 更新本地软件源 apt-get update
    1. 软件包安装 apt-get install sl
    1. 软件包卸载 apt-get remove sl
    1. 软件包彻底卸载 apt-get remove --purge sl
    1. 二进制软件包下载 apt-get download sl
    1. 软件包源码下载 apt-get source sl
    1. 查看软件包的安装状态 apt-cache policy sl
    1. 查看软件包的信息 apt-cache show sl （无论是否安装）
    1. 升级软件包 apt-get upgrade
    
    注：用于在线安装、卸载以及查询软件包的相关信息，只要配置正确就可以通过网络来进行软件包的在线安装，这种方式就可以很好的解决软件包之间的依赖关系。
    
    相关配置文件:
    * /etc/apt/sources.list，包含deb软件包源的文件
    * /var/lib/apt/list/* 对软件源进行更新之后的本地文件
    * /var/cache/apt/archive，在线安装时软件包的下载目录
    * /var/log/dpkg.log，本地软件包管理的日志文件
    * /var/log/apt/ * .log,在线软件包管理的日志文件
    
### openssh

1. 安装:sudo apt install openssh-server openssh-client
2. 登录:ssh 用户名@ip地址
3. 传输:scp (-r针对目录)　文件(目录)　用户名@ip地址：路径
