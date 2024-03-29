---
layout: page
title: 解决MacBook Pro电池无法充电的问题
category: life
tagline: --read & think
tags : [MagSafe,Mac]
---
{% include JB/setup %}

今天下雪了。本来应该高兴的，然后就发现MacBook Pro没办法充电了。-_-#

本来电池还剩不到10%的电，接上电源适配器却一直显示绿灯。此时，菜单栏中电池状态显示“电源已接通未充电”，并且是电源适配器供电。一句话，电池不能充电了！

首先去官网“技术支持”查。在[故障诊断 MagSafe 适配器问题](http://support.apple.com/kb/TS1713?viewlocale=zh_CN)和[全面了解电池](http://support.apple.com/kb/HT1446?viewlocale=zh_CN#Troubleshooting)中都提到了`电池无法充电`的问题，但给出的解决方法都不行。最后在[Mac 笔记本电脑：工作温度](http://support.apple.com/kb/HT1778?viewlocale=zh_CN)找到了真正的原因。

> 您使用笔记本电脑的环境应该在以下这些范围内：
> 
> 操作温度：50° 至 95° F（**10° 至 35° C**）
>
>相对湿度：0% 至 90%，非冷凝

**原来是温度过低的问题。**

当电池温度低于10℃时，采用大电流快速充电，会影响电池的寿命。因此一些笔记本（甚至是手机）会设定一个`最低温度`，当设备温度低于最低温度时，设备会自动启动电池保护——即对电池断电（据说Kindle也是这样）。

抛去硬件损坏的情况，现在MacBook系列电池无法充电，MagSafe电源适配器一直显示绿灯的原因，一般有两种：

1.环境温度太低，电池自动保护。<del>这种情况冬天出现较多<sup>废话</sup></del>。这时最简单的方法就是使用一段时间或是放于温度较高的室内，机器温度提升后自动会充电；

2.环境温度大于电池充电温度，但MagSafe电源适配器仍显示绿色，不能充电。出现这种情况就不是气温低的原因了，是因为系统管理控制器（SMC：System Management Controller ）出了问题，此类问题可以通过重置SMC解决。

下面是重置SMC的方法，参考资料：[基于 Intel 的 Mac：重置系统管理控制器（SMC）](http://support.apple.com/kb/HT3964?viewlocale=zh_CN)

> 重置 SMC 之前，请按顺序尝试以下各步骤。在完成各故障诊断步骤之后，请进行测试以确定问题是否仍会出现。
> 
> 1、按下 Command + Option + Escape 强制退出任何没有响应的应用软件。
> 
> 2、从左上方菜单栏中选取 Apple () 菜单，然后选取睡眠，以将 Mac 置入睡眠状态。待电脑进入睡眠状态后，将其唤醒。
> 
> 3、从左上方菜单栏中选取 Apple () 菜单，然后选取重新启动，以重新启动 Mac。
> 
> 4、从左上方菜单栏中选取 Apple () 菜单，然后选取关机，以关闭 Mac。
> 
> 如果按照上述故障诊断步骤操作后仍未能解决此问题，则可能需要重置 SMC。
> 
> 1、	关闭电脑。
> 
> 2、	将 MagSafe 电源适配器连接到电源和 Mac（如果尚未连接的话）。
> 
> 3、	在内建键盘上，同时按下（左侧）Shift-Control-Option 键和电源按钮。
> 
> 4、	同时松开所有键和电源按钮。 按下电源按钮打开电脑。
>
>  注：重置 SMC 时，MagSafe 电源适配器上的 LED 指示灯可能会更改状态或暂时关闭。