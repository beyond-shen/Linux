# 关于linux中一些工具的安装和环境的配置

## vim和git的安装 

```
$ sudo apt-get install git  vim -y
```

### 安装 git 下载运行需要安装软件的sh
```
 $ sudo apt-get install git -y
 $ git clone https://github.com/wangleihd/software.git
 $ cd software
 $ chmod 755 software.sh
 $ ./software.sh
 $ ./install.sh
```

## ssh的安装

```
$ sudo apt-get install openssh-server
```

## 更新数据源

```
$ sudo apt-get update
```

## apache服务器的安装和配置

### 安装tasksel

```
$ sudo apt install tasksel
```
###  使用tasksel 

```
$ sudo tasksel
```
选择LAMP server选项， 安装过程中需要设置mysql数据的root密码， 统一设置为123456

### 重启apache 

```
$ sudo /etc/init.d/apache2 restart 
```

## 进入Linux系统的超级用户(root)

1. 激活超级用户

sudo passwd root

2. 切换到root用户

su -

3. 退出root用户

exit
