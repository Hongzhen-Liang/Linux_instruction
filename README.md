# linux指令

1. 常规指令
	* 下载：`wget -P /tmp url`
	* 删除: `rm -rf 文件名`
	

2. 安装Anaconda：
	* 相关网站教程:https://blog.csdn.net/weixin_44776894/article/details/106159483
	* 官网:https://www.anaconda.com/products/individual
	* 下载：`wget -P /tmp https://repo.anaconda.com/archive/Anaconda3-2020.07-Linux-x86_64.sh`
	* 安装：`bash /tmp/Anaconda3-2020.07-Linux-x86_64.sh`
	* 加载环境变量: `source ~/.bashrc`
	* 升级Anaconda：`conda update --all`

3. SSH服务:
	1. 安装
		* `sudo apt-get install openssh-client`
		* `sudo apt-get install openssh-server`
		* 启动:`sudo /etc/init.d/ssh start`
		* 查看：` ps -e | grep ssh`
		* IP地址查看：`ifconfig -a`
		* 配置设定`sudo vim /etc/ssh/sshd_config`：
			1. 密码登录：`PasswordAuthentication yes`
			2. root用户运行：#PermitRootLogin prohibit-password下增加`PermitRootLogin yes`
	2. 使用
		* 远程登录：`ssh user@ip`
		* 指定端口登录： `ssh user@ip -p 端口`
		* 复制：`scp -r usr@43.224.34.73:/home/lk   /root`  //将 /home/lk 文件拷贝到本地 /root 
		* 上传：`scp /root/test.jar   usr@43.224.34.73:/home/lk`
		* 退出：`exit`
		* 内网映射：
			1. frp
			2. 花生壳：https://console.hsk.oray.com/ （当前映射www.sinscry.tech:25319）
	
	3. 错误：
		* 无法连接时：`sudo vim ~/.ssh/known_hosts`，删除ip地址那行数据
	