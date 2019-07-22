#利用PMOD_ALS 做路灯自动控制照明实验

​	在做这个实验之前，我们需要一个PMOD_ALS传感器，将其插入FPGA 板子的上接口即可。

​    如图

​	![avatar](C:\Users\何锦华\Desktop\20190722155742.jpg)

 再编辑代码，我的代码已经上传到Jupyter的example文件夹，代码文件是【PMOD_ALS by hejinhua】

在测试如下，在环境光下，LEDs一直亮着,当把手机电筒对着PMOD传感器模块时，LEDs熄灭，说明达到了想要的效果。

​	环境光下

![avatar](C:\Users\何锦华\Desktop\20190722155801.jpg)

​		手机电筒照明下

![avatar](C:\Users\何锦华\Desktop\WIN_20190722_16_07_03_Pro.jpg)