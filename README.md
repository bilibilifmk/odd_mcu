# 奇怪的MCU/ESP8266开发板-----开发中！！！！！！！！
## 拥有充电，电量检测以及两个额外的ADCio等功能的esp8266开发板
### 注意本开发板没有自动烧录可能对新手不算友好，但是有效解决误刷入

![image](https://github.com/bilibilifmk/odd_mcu/blob/master/img/pcb1.png) ![image](https://github.com/bilibilifmk/odd_mcu/blob/master/img/pcb2.png)
![image](https://github.com/bilibilifmk/odd_mcu/blob/master/img/pcb3.png) ![image](https://github.com/bilibilifmk/odd_mcu/blob/master/img/pcb4.png)



## 原理图
![image](https://github.com/bilibilifmk/odd_mcu/blob/master/img/ylt.png)

## 材料清单
![image](https://github.com/bilibilifmk/odd_mcu/blob/master/img/clqd.png)

## 可选部分
ADS1115 造价较贵 作为可选原件 不使用 D1 D2将会变成普通io  
不使用会导致无法使用的功能：1.不能识别供电模式 2.不能使用电量检测（可以用A0代替）3. A1 A2 将会失效 R1-R4电阻不用焊接  
如果不使用1115还想保留电池电量检测功能需要补全一下电路（可在板子背面飞线焊接）  
![image](https://github.com/bilibilifmk/odd_mcu/blob/master/img/a0.png)

## 电器特性
1.供电部分部分：  
usb输入电压5v 电池最大充电电流1A（芯片TP4056）电池最大电压4.2v  
2.io接口部分：  
电源口：usb引脚为输入5v电压 直通micro usb输入正极    
g为整体负极   
3.3为稳压管输出也可做为输入3.3（作为输入3.3会跳过充电等电路）    
bat为电池输出  
gpio：A1 A2 具有0-5v输入耐压（模拟输入）  
A0为普通adc最大承受3.3v    
D0 D3-D8 为普通io 最大承受3.3v （可抗瞬时5v）    
D1（scl） D2（sdc） 为i2c接口 不可用于普通接口（在不使用ADS1115情况下为普通io）  
