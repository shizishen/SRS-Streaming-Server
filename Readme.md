配置环境：ubuntu22.04

#注册使用阿里云服务器

[阿里云免费试用 - 阿里云](https://free.aliyun.com/?spm=5176.28508143.J_ahRFo5CaAe_asSOaCgS4J.8.5421154ayOo0mW)

1.通过官方教程开通一个服务器[部署并使用Docker-阿里云帮助中心](https://help.aliyun.com/document_detail/2341651.html?spm=5176.28008736.J_7597446870.d10000006670_1.1ff43e4dpxRi8M&scm=20140722.M_10000006670.P_121.MO_2230-ID_10000006670-MID_10000006670-CID_0-ST_8726-V_1)，新用户有免费3个月

2.选择好自己需要的系统和配置之后，点击试用后，在自己的实例中可以查看到自己的公网ip地址，例如114.55.229.122

#finalshell连接阿里云服务器

1.[下载脚本](http://www.hostbuf.com/downloads/finalshell_install_linux.sh)

2.ctrl + alt + T 打开终端，授权安装脚本可执行权限

chmod u+x finalshell_install_linux.sh

3.运行脚本

./finalshell_install_linux.sh

4.finalshell安装成功

![Screenshot_20231214_193331.png](/home/lsw/图片/Screenshot_20231214_193331.png)

5.打开finalshell，连接阿里云服务器

![Screenshot_20231214_193444.png](/home/lsw/图片/Screenshot_20231214_193444.png)

![Screenshot_20231214_193528.png](/home/lsw/图片/Screenshot_20231214_193528.png)

6.输入阿里云公网IP地址114.55.229.122，端口号默认不用改，用户名随意填，密码可以在阿里云服务器中重新设置

![Screenshot_20231214_193709.png](/home/lsw/图片/Screenshot_20231214_193709.png)

7.连接成功

![](/home/lsw/snap/marktext/9/.config/marktext/images/2023-12-14-19-40-17-image.png)
