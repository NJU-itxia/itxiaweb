# 服务器概述
感谢yzh学长的资瓷，我们双十一在腾讯云购入了一台性能不错的服务器.
## 连接服务器
安全起见，不在这里记录服务器的IP地址，问群里要.
服务器不允许使用密码登录，必须用密钥登录.
需要密钥可以在内群里联系组长要.
### 连接方法
#### Linux/WSL连接方法
将密钥放到~/.ssh文件夹下.
接下来配置**ssh config**:
修改 ~/.ssh/config，添加
```
Host {服务器昵称}
	HostName {服务器IP地址}
	User {服务器用户名}
    Port {ssh端口}
	IdentityFile {密钥路径}
```
修改后，只需要
```bash
ssh {服务器昵称}
```
即可连接.
昵称还支持**tab自动补全**!
#### VS Code 远程连接
同上，将密钥放到指定位置，配置ssh config即可.

## 环境/软件
配置了常用的环境.
### apt
**运行apt-get upgrade前慎重考虑!**
升级一些软件可能会把软件停掉，比如升级docker可能会把正在运行的docker关掉.
升级前谨慎考虑.

### docker 
已经配置了USTC的docker hub镜像源.
apt里的docker版本太老，使用官网的docker-ce版本.

### mysql
不要修改、删除数据库.
可以添加数据库、添加用户.
使用apt的5.7.x版本.

### java
openjdk的java 11.

### nodejs
apt里的nodejs, npm版本都太老，使用官网的版本.

### python2/3
python命令是python2.
|命令|是啥|
|---|---|
|python|python 2.x|
|python3|python 3.x|
|pip|python 2.x的pip|
|pip3|python 3.x的pip|
