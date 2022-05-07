# 2021-05-03-Centos服务器搭建VNC环境
---
建议xshell 通过SSH协议连接centos主机，然后执行如下命令（解释见下文）：
！[命令行截图1](https://img-blog.csdnimg.cn/7e11e1a8831547149f75d20c3d1eb376.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBATm92YWMuaGU=,size_20,color_FFFFFF,t_70,g_se,x_16)


第227、228为安装vim命令包

修改配置文件vncserver@\:1.service，直接修改如下两行，将<USER>替换成root
```
ExecStart=/usr/sbin/runuser -l root -c "/usr/bin/vncserver %i"
PIDFile=/root/.vnc/%H%i.pid
```
231行建议将VNC密码设置成123456，不设置view-only密码

236行为安装网络工具，可以执行netstat命令

执行完237行后就知道我们需要5901作为VNC端口，就可以在VNC工具中测试连接远程主机。

连接成功的图片如下：
![VNC连接成功1](https://img-blog.csdnimg.cn/f1f6843986454ede8194ba81783afef7.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBATm92YWMuaGU=,size_11,color_FFFFFF,t_70,g_se,x_16)

![VNC连接成功2](https://img-blog.csdnimg.cn/004329af2a9d4cac9b418ece100937f1.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBATm92YWMuaGU=,size_20,color_FFFFFF,t_70,g_se,x_16)


其中需要注意的是：

在编写service脚本时，如果缺少某一行，则要补齐少的行。
在VNC客户端安全菜单中，关掉加密；
端口一点要与查询出的一致，这里写5901；
账号就是在那个service脚本中修改的用户，这里是root。
