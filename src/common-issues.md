# 常见问题

因此，如果某些内容无法正常工作，您会发现自己陷入困境，那么本页面将提供常见问题的答案。如果这里没有回答您的问题，请随时在[#support-forum](https://discord.com/channels/817184208525983775/1025104406393405491) on the [SlimeVR Discord](https://discord.gg/slimevr)中提问。在寻求帮助时，请确保提及您从这里尝试的所有步骤。

* TOC
{:toc}

## 在更新固件/尝试上传固件时，请指定upload_port

此错误表示您的计算机和追踪器之间存在干扰。请检查以下内容：

1. 确保您从追踪器到计算机的USB电缆已牢固插入。
1. 确保您的USB电缆是数据和充电电缆（建议您尝试使用其他电缆或设备）。!!!有些线缆仅包含充电功能，不包含数据传输!!!
1. 确保您的驱动程序已更新到最新版本。

此外，这可能是由软件独占COM端口引起的(**VSCode和Cura可能是原因**)。

## SlimeVR服务器无法启动

- 如果出现端口错误，请确保没有其他服务器实例正在运行和/或重新启动计算机。
- 这也可能是由于未安装Java或Java安装存在问题引起的。链接到 [安装服务器页面](server/initial-setup.md#install-the-latest-slimevr-installer)的安装程序应处理此问题。

## Wi-Fi设置窗口输出ERROR

尝试重置追踪器，这可能会立即解决问题。如果这不起作用，则可能正在独占COM端口，可以通过在VSCode中执行固件更新过程（因为它具有更详细的错误消息）进行测试。如果是这种情况，请关闭可能独占端口的任何应用程序（VSCode和Cura通常是原因）。如果问题仍然存在，请尝试将追踪器连接到另一个USB端口。

## Wi-Fi设置窗口输出符号而没有其他内容

有两个常见原因需要检查：

- 确保已安装正确的驱动程序。
- 检查您的PIO固件上传是否成功。如果在VSCode中打开了多个固件版本，则必须将正确的版本设置为默认以进行上传。

## 我的追踪器一直在闪烁

这是正常的，闪烁次数可以让您了解追踪器的当前状态。请查看[设置页面顶部以获取更多信息。](server-setup/initial-setup.md#test-your-trackers).

## 我的追踪器从未连接到Wi-Fi/未出现在SlimeVR服务器上

导致此错误的两个常见问题是：

- 确保您连接到2.4GHz网络，追踪器不支持5GHz网络。
- 检查您的SSID是否包含特殊字符。在编写本文时，SlimeVR仅支持包含字母数字字符的网络SSID。

如果所有这些都正确，则可以检查网关的连接设备列表，以查看所有追踪器是否连接。如果即使在使用硬编码的Wi-Fi详细信息进行相同的固件上传后，追踪器仍未连接，则可以检查两个其他步骤：

- 检查您的Wi-Fi是否已达到其允许的最大Wi-Fi连接数。您可以通过断开设备然后再次尝试连接追踪器来测试此功能。
- 如果在 `platformio.ini` 中硬编码了Wi-Fi设置，请尝试通过USB连接追踪器并 [设置新的Wi-Fi详细信息](server/connecting-trackers.md#connect-trackers). 您可能会发现这要么修复了您的连接，要么为您提供了有关为什么连接失败的其他详细信息。

## 我的辅助追踪器不起作用

为了确保设置了辅助追踪器，您需要在上传到主要追踪器固件的 `defines.h` 中指定它。请检查 [配置SlimeVR固件页面底部提到定义选定板上引脚部分](firmware/configuring-project.md#define-pins-of-the-selected-board)。或者，您应确保已将VCC正确焊接到辅助追踪器IMU上的AD0。

## 传感器已重置错误

检查您的INT线路，存在错误连接或将其连接到闪存引脚。如果您正在面包板上构建跟踪器，则可能会导致连接不够牢固而导致此错误。

## 追踪器已连接到我的Wi-Fi但未出现在SlimeVR上

请确保没有两个副本的SlimeVR服务器正在运行，因为只有一个副本会显示已连接的跟踪器。

如果只有一个服务器正在运行，则最可能是防火墙问题，请转到SlimeVR Server文件夹并以管理员身份运行`firewall.bat` 以将防火墙规则添加到Windows Defender防火墙中。

如果仍然遇到问题，请尝试手动将SlimeVR Server添加到防火墙中。

1. 去到 **设置** > **网络和Internet** 然后点击 **Window防火墙** (你可能需要下滑).
1. 在防火墙窗口中, 点击 **允许应用通过防火墙**.
1. 点击 **允许其他应用...** 按钮, 然后点击 **浏览...** in the opened **Add an app** window. If your options are greyed out in the **Allowed apps** window, click the **Change Settings** button to allow changes.
1. In the **File name** text box, type `*.*` and press enter before navigating to `slimevr.jar` in your SlimeVR server folder and select it (if you cannot see files in this folder, try typing `*.*` and pressing enter again to show all files).
1. Click the **Add** button to add the file to your firewall settings.
1. Finally, make sure both public and private check boxes are selected in the **Allowed apps** window before clicking **OK** to save the changes.

If adding SlimeVR to your firewall has not worked, you can try to diagnose the issue further with the following steps:

1. Try completely disabling Windows Defender Firewall on your computer temporarily to test if the trackers will connect.
   - If the trackers only show up on SlimeVR when Windows Defender Firewall is disabled, then you have a problem with your firewall.
1. Try pinging the tracker from your computer to see if it can be reached by opening Command Prompt (CMD) and run the command `ping <IP>`, where `<IP>` is your tracker's IP (ex. `ping 192.168.0.1`). You can find the tracker's IP using the "Serial console" under the "Settings" tab of the SlimeVR GUI.
   - If the command outputs something like `Reply from 192.168.XXX.XXX: Destination host unreachable.`, then you likely have a problem with either your router or your firewall.
   - If the command outputs something like `Reply from 192.168.XXX.XXX: bytes=32 time<1ms TTL=63`, then you likely have a problem with either your network adapter or your network settings. You may need to enable broadcast packets (or something similar) on your router, as SlimeVR trackers broadcast to `255.255.255.255` to discover your SlimeVR Server.
1. Try hosting a Wi-Fi hotspot either from your computer or your phone and connect your trackers to it to see if they will show up on SlimeVR using it.
   - If the trackers don't show up on SlimeVR, then you likely have a problem with either your trackers or your computer. It may be worth trying disabling your Windows Defender Firewall as per the first step, but using this Wi-Fi hotspot instead.
   - If the trackers show up on SlimeVR, then you likely have a problem with either your router or the network adapter you connect to your router with.

If none of these steps have helped you, you can find information about getting further help at [the top of this page](#common-issues).

## The trackers are connected to the SlimeVR server but aren't showing up

This is usually the result of an issue with the IMU. Plug in your Wemos D1 Mini and check through the serial console under settings in the SlimeVR server. You may see an error like one of the following:
```c
[ERR] I2C: Can't find I2C device on provided addresses, scanning for all I2C devices and returning
[ERR] I2C: No I2C devices found
[ERR] I2C: Can't find I2C device on provided addresses, scanning for all I2C devices and returning
[DBG] I2C (@ D2(4) : D1(5)): I2C device found at address 0x68  !
[ERROR] [ErroneousSensor:0] IMU of type MPU6500 failed to initialize
```

The most common reasons for errors with the IMU are the following:

1. You accidentally set the IMU wrong (i.e. set as MPU6050 when you have an BNO085)
1. You accidentally selected the wrong board type (i.e. set as BOARD_SLIMEVR instead of BOARD_WEMOSD1MINI)
1. The wiring is wrong (e.g. accidentally swapping around D1/D2 and SDA/SCL)
1. There's an issue with the soldering (e.g. not enough solder, cold joint, or bridging between SDA and SCL)
1. You're using a breadboard (Without soldering connections, the IMU often won't be able to communicate with the microcontroller)
1. There's an issue with the IMU itself (e.g. burned trace while soldering, or the chip is downright DOA)

## The trackers are connected to the SlimeVR server but aren't turning up on Steam

- Make sure you installed SlimeVR with [the installer](https://slimevr.dev/download) to have the right SteamVR driver.
- Make sure the SlimeVR addon is enabled in SteamVR Settings > Startup/Shutdown > Manage Add-ons.
- Make sure you have [SteamVR Trackers clicked](server/configuring-trackers.md#configuring-how-many-virtual-trackers-you-need).

## My trackers are bound to the wrong body part in SteamVR

- If this is in-game, this is probably due to a calibration issue.
- If this is in SteamVR, go to Settings > Controllers > Manage Vive Trackers, and manually set up the trackers' positions to match the virtual trackers' names.

## Your trackers are drifting more than expected

Make sure that when you turn on your tracker, it's lying on a flat surface. The sensors need to calibrate for 10-20 seconds in a stable environment.

## My feet sink into the floor / I'm sliding a lot

This will be due to either your physical or bone length set up. Try:

- Running AutoBone again.
- Other suggested mounting points.
- Adjusting your bone lengths manually by following the [step shown here](server/body-config.md#configuring-body-proportions-manually).

## Trackers are moving in the wrong direction when I move

- Make sure your mounting orientations for your trackers in the server are correct. (you might have to lie about them for certain setups)
- You may have specified a wrong `IMU_ROTATION` value in your `defines.h` file. Take note of which trackers are the issue and refer to the [configuring the SlimeVR firmware page](firmware/configuring-project.md#adjust-imu-board-rotation) to get the board's rotation right.
- If it’s only off by a few degrees, shift your trackers inwards or outwards a bit, then full reset.

## My avatar floats above the ground

- Make sure your floor level is correct using OVRAdvancedSettings' fix floor function.
- Increase your user real height in VRChat or any equivalent setting in other games.

## My legs don't bend

- Make sure you have upper leg trackers above your knees and assigned as "upper leg" trackers as well as lower leg trackers below your knees assigned as "lower leg" trackers.
- Make sure your lower legs trackers are on your lower legs and not your feet.

## My legs cross when sitting down

- Try mounting your upper leg trackers more inwards.
- Try mounting your upper leg trackers higher on your thighs or lower on your upper legs depending on your build.
- Calibrate with your legs straight and a normal hip width (24-32) in your body proportions.
- Use fast reset to correct leg crossing: [assigning a keybind for resetting](server/setting-reset-bindings.md).

## One of my leg is higher than the other

Shift your upper leg trackers a bit, try out other mountings for your upper leg trackers

## AutoBone / Automatic body proportions calibration isn't working

If AutoBone isn't working properly for you, you can find a list of common issues and debugging information in the ["Common Issues / Debugging" section of the body proportions configuration page](/server/body-config.md#common-issues--debugging).

## SlimeVR is stuck at "Connecting to the server"

If your SlimeVR GUI is never loading past "Connecting to the server", it is likely that your SlimeVR configuration file is invalid. You can try deleting or moving the `vrconfig.yml` file in your SlimeVR install folder (generally located at `C:\Program Files (x86)\SlimeVR Server` on Windows) and running SlimeVR again to generate a new configuration file.

Please note that you **will** lose your configuration if you decide to delete the `vrconfig.yml` file. If you wish to retain the invalid configuration file, you may either rename or move the file to a different location, then run SlimeVR again to generate a new configuration file.

## The SlimeVR window is stuck as a tiny window

This is a bug in the framework we're using. To solve it, navigate to `%appdata%\slimevr.dev` and delete `.window-state`

## WebView2 is missing / SlimeVR GUI crashes immediately / "panicked at ... WebView2Error"

It's possible that you don't have the required WebView2 component installed, you can download the WebView2 installer from <https://developer.microsoft.com/en-us/microsoft-edge/webview2/consumer/>. To ensure that WebView2 installs properly, run the WebView2 installer as an administrator (right click, then click "Run as administrator") and make sure the installer is running from the C: drive on your computer. If it's still not working, try putting the installer in the root of the C: drive (ex. `C:\MicrosoftEdgeWebview2Setup.exe`) and running it from there.


## References

* [BNO08X calibration documentation](https://xdevs.com/doc/CEVA/BNO080-BNO085-Sesnor-Calibration-Procedure.pdf)
* [MPU-9250 product specification](https://invensense.tdk.com/wp-content/uploads/2015/02/PS-MPU-9250A-01-v1.1.pdf)

*Created and updated by CalliePepper#0666, edited by Emojikage#3095, Spazzwan#0001, Butterscotch!#0226*
