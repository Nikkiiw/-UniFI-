# 解决Unifi Network Application无法启动的问题
Unifi Network Application只能在首次安装后成功启动，经查看是java的路径问题。解决方法如下。
在软件根目录下新建runjava.bat，内容如下
````
java -jar ace.jar ui
````
运行即可。

以上的 bat 脚本双击运行后会出现黑色 cmd 的终端窗口，若不想出现该窗口，可让其后台启动运行，这样就可以避免不小心关闭了创建运行，即可在脚本开头加入以下代码：
````
if "%1"=="h" goto begin
start mshta vbscript:createobject("wscript.shell").run("""%~nx0"" h",0)(window.close)&&exit
:begin
````

