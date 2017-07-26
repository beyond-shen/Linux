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

## nodejs

### nodejs的安装

```
$ curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
 $ sudo apt-get install -y nodejs
```

### 开发环境的安装

```
 $ sudo apt-get install -y build-essential
```

## npm 

NPM是随同NodeJS一起安装的包管理工具，能解决NodeJS代码部署上的很多问题

1. 允许用户从NPM服务器下载别人编写的第三方包到本地使用。
2. 允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用。
3. 允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用

### npm的常用命令

#### 创建package.json文件

在scripts字段中除了start不需要加run，其他都需要npm run 
```
$ npm init -y
```
#### 安装模块

1. 全局安装带（-g）,强制安装带（-f）
2. 本地安装到该目录下的node_modules的目录里并保存到package.json中的dependencies，命令如下：
```
$ npm install express --save
```
#### 如果本地没有模块但是package.json中有，那么可以使用

```
$ npm install 
```

## nvm

对node版本的管理

### 安装

```
$ curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
```

### 环境配置

打开~/.zshrc或者在Ubuntu 打开 ~/.bashrc，最后添加如下代码
```
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh" # This loads nvm
```
### 重启

目的：这一步的作用是每次新打开一个bash，nvm都会被自动添加到环境变量中了
```
$ . ./bashrc  
或者重新打开终端
```

### 常用命令

1. nvm --version: 查看nvm版本
2. nvm ls-remote：查看远程有多少个node版本
3. nvm ls:查看当前使用的是哪个版本
4. nvm install (-s) version:安装指定的版本的node
5. nvm use:切换使用版本，默认是system

## 安装全局的express

```
$  sudo  npm i express-generator -g    //express-generator: 一个提供在命令行中快速搭建应用的全局NPM包.
```
