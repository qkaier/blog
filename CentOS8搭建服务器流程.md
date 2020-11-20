### CentOS8搭建服务器流程
1. 关闭selinxu。
	`cd /etc/selinux`

2. 关闭防火墙。
   `systemctl stop firewalld.service
    systemctl disable firewalld.service`

3. 安装nginx
   `yum install nginx
    yum start nginx
	yum enable nginx`

4. php php-pfm 以及相关组件
   `yum install php php-fpm php-opcache php-gd php-xml php-mbstring php-json`
   `systemctl start php-fpm`
   `systemctl enable php-fpm`
   `systemctl restart nginx`

5. 编辑php-pfm配置文件，以nginx用户运行
   找到下面两行:
   `user = nginx
    group = nginx`
   `systemctl reload php-fpm`

6. 用phpinfo测试环境

7. php文件最大上传大小修改
   `/etc/php.ini`

8. 多域名配置
   [配置文件](./file/nginx.conf)
	

