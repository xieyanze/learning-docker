为什么需要创建docker用户组？

Docker守候进程绑定的是一个unix socket，而不是TCP端口。这个套接字默认的属主是root，其他是用户可以使用sudo命令来访问这个套接字文件。因为这个原因，docker服务进程都是以root帐号的身份运行的。
为了避免每次运行docker命令的时候都需要输入sudo，可以创建一个docker用户组，并把相应的用户添加到这个分组里面。当docker进程启动的时候，会设置该套接字可以被docker这个分组的用户读写。这样只要是在docker这个组里面的用户就可以直接执行docker命令了。
警告：该dockergroup等同于root帐号，具体的详情可以参考这篇文章：Docker Daemon Attack Surface.
操作步骤：
使用有sudo权限的帐号登录系统。
创建docker分组，并将相应的用户添加到这个分组里面。
sudo usermod -aG docker your_username
退出，然后重新登录，以便让权限生效。
确认你可以直接运行docker命令。
$ docker run hello-world
