#智能路灯——我的学习日志
##黄静远 2019.7.24

##实验的硬件部分
    这个实验使用的是pynq板，附加了插在PmodB上的光传感器模块。
##实验的代码部分
    这个代码比较简单，可以全部列出
'''
from pynq import Overlay
Overlay("base.bit").download()
from pynq.iop import Pmod_ALS
from pynq.iop import PMODB
from time import sleep
from pynq.board import LED
from pynq.board import Button

my_als = Pmod_ALS(PMODB)
Delay = 1
leds = [LED(index) for index in range(4)]
btns = [Button(index) for index in range(4)]

my_als.read()

while btns[3].read()== 0:
    if my_als.read() < 50:
        for led in leds:
            led.on()    
    else:
        for led in leds:
            led.off()
    sleep(Delay)

print('End of this demo ...')
for led in leds:
    led.off()

del leds,btns
'''
    使用了Pmodzhong的als模块、pynq中的LED、Button模块。用来输入光传感信息、开关信号，输出led亮灭信号。
##实验中遇到的问题
    一开始，my_als.read()输出的始终为255，询问助教后得知是光传感器接错了位置，应该插在PmodB的上端接口，否则将一直显示未接入。
