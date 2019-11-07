
19/11/06</br>

1.安装Tomcat 9</br>
2.安装MyEclipse 2019.4</br>
***

首先安装Tomcat9，在[链接](http://tomcat.apache.org/)下载Windows Service Installer</br></br>
然后再安装MyEclipse。安装完成后打开MyEclipse，在软件Window->Preferences->Servers->Runtime Environment中添加Tomcat服务器</br>
  点击Add->Tomcat->Apache Tomcat V9.0（勾选上Create a new local server）点击Finish，之后选择Tomcat的目录，点击Finish就完成
  Tomcat服务器的安装了。</br></br>
Window->Preferences->File and Editors->JSP中将Encoding改为ISO 10646/Unicode(UTF-8)然后确认，就完成了JSP文件默认为UTF-8模式</br></br>

在程序中打开Tomcat服务器可能会遇到`The server cannot be started because one or more of the ports are invalid. Open the server editor and correct the invalid ports.`这个问题，</br>
解决方法，找到Tomcat安装目录->conf->编辑server.xml，找到`<Server port="-1" shutdown="SHUTDOWN">`将`-1`改为`8005`保存即可</br></br>

也可能会遇到`Port 8,080 required by Tomcat v9.0 Server at localhost is already in use....`意思就是8080端口被占用，打开CMD，输入`netstat -ano|findstr 8080`查看占用8080端口号的程序PID，然后进入任务管理器->详细情况->PID排序，找到CMD中的PID，结束任务即可解决
