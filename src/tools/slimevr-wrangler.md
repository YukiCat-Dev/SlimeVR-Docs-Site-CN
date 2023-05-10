# SlimeVR Wrangler

这个指南将会指引你安装并使用SlimeVR Wrangler,一个能够使用Joycons作为SlimeVR追踪器的应用。

![Screenshot of the app running and tracking a single Joy-Con](../assets/img/SlimeVR_Wrangler.png)

## 安装
你的电脑需要有蓝牙接收器。
* 下载并安装配置 [SlimeVR](../server/initial-setup.md)
* 下载 [SlimeVR Wrangler](https://github.com/carl-anders/slimevr-wrangler/releases/latest/download/slimevr-wrangler.exe)
* 打开 SlimeVR server 和 SlimeVR Wrangler
* 连接你的Joy-Con 追踪器 到电脑 ([Guide for Windows](https://www.digitaltrends.com/gaming/how-to-connect-a-nintendo-switch-controller-to-a-pc/))
* 确保SlimeVR Server正在运行,然后点击 "Search for Joycons"
* 你的Joy-Con应该会出现在窗口内。
* [在SlimeVR Server中设置新的追踪器](../server/connecting-trackers.md)

### 穿戴

确保你的手柄摇杆指向外边，而不是戳向你的皮肤。

在程序连接上你的手柄后，请将其Rotate（旋转）设置到和你实际佩戴一致的方向和角度。

用最适合你的方向来安装佩戴, 参考 [putting on your trackers](../server/putting-on-trackers.md) 来查看安装方向和追踪器分配的说明。

## 问题

有很多! 这仍然是个 **alpha** 版本, 没有人能保证会发生什么！

* 旋转追踪很差! - 是的，很抱歉. 在未来应该会有设置可以微调追踪。 建议所有人 [绑定一个重置按键](../server/setting-reset-bindings.md)
* 一转身就丢追踪了! - 蓝牙的信号接收范围不好, 换一个蓝牙接收器可能效果都会不一样。
* 可能还有很多未知问题。

### My Joy-Con's are connected in the Windows bluetooth menu but won't show up!

This is a problem that might be related to a newer Windows update. Try this, and it might fix it:
* Go to the Windows Setting app -> Bluetooth & other devices.
* Press on the Joy-Con that won't connect. Press "Remove device".
* Pair the device again. It should now show up.


*Created by Carl (<https://github.com/carl-anders>), edited by NWB#5135*
