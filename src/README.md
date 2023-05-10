# SlimeVR文档

欢迎来到SlimeVR文档. 本站介绍如何 [制造你自己的 SlimeVR 追踪器](diy/index.html), [安装或更新现有追踪器固件](firmware/index.html), [安装并配置SlimeVR服务器](server/index.html), and [提供广泛的社区构建工具集合](tools/index.html).

> **批注:** 你需要至少5个追踪器来实现全身追踪 (FBT). 或者, 如果你想测试腰围追踪功能，你可以构建一个单独的腰部追踪器，而无需购买完整的套件。也存在其他方案 (例如使用手机或joycons), 但这些选项会受限于你使用的设备, 可能会效果不佳。

## 什么是SlimeVR?

SlimeVR是一组开放硬件传感器和开源软件，可在虚拟现实中实现全身跟踪（FBT）。该项目的构建围绕着创建一个可定制、可黑客和可修改以适应用户需求的系统。因此，本文档不仅提供了如何设置您的环境的完整说明，还提供了如何自己构建一组跟踪器的完整说明。有关系统如何工作的更详细说明，请查看[SlimeVR 101](slimevr101.html).

## 如何获得这些甜蜜的SlimeVR追踪器？

目前有多种方法可以使用SlimeVR组装自己的FBT解决方案。

### 1. 购买追踪器

#### Fully built trackers directly from SlimeVR

![Slime Trackers](assets/img/slimeVRTrackers.jpg)

您可以在[Crowd Supply](https://www.crowdsupply.com/slimevr/slimevr-full-body-tracker)上预订完整的追踪器。这些追踪器是SlimeVR专注核心成员的热情项目，由于芯片短缺、运输延迟等原因，我们无法保证发货日期或周转时间。

此选项是预订。请查看产品页面以获取新订单的预计发货时间。实际发货时间可能因生产延误和其他情况而有所不同。

#### 第三方卖家

第三方销售商正在变得越来越普遍, 订购可以在 [SlimeVR discord](https://discord.gg/SlimeVR) 市场论坛上找到。设计和规格因供应而异，因此请确保检查您获得的内容！由于追踪器最重要的方面之一是IMU（用于测量您的运动），我们建议您查看 [IMU 比较页面](diy/imu-comparison.html)以了解任何可用追踪器的预期。

> **注意:** SlimeVR无法确保第三方追踪器符合任何质量要求，请假定从第三方销售商购买相当于从小型创作者购买，您自己对这些追踪器的质量进行研究非常重要。我们建议您查看评论或与已经从卖家那里购买过的其他人交谈，以了解预期。如果您购买的任何第三方追踪器出现故障，请联系卖家寻求帮助。但是，您可能需要一些焊接理解才能自行修复它们。

### 2. 自己构建

#### 完全从零开始

![Example DIY build](assets/img/exampleBuild.jpg)<br>
*Example build by NightyIceC00kie*

在撰写本文时，构建追踪器是用户拥有追踪器的最常见方法。本文档提供了一个完整的[从头开始构建追踪器的指南](diy/index.html), 其中提供了所需的完整组件列表、购买它们的位置以及许多IMU和微控制器组合的原理图。

这是获得追踪器最便宜、最快速的方法，假设您手头有一个焊铁，一个单独的追踪器可以花费不到20美元。

DIY构建需要时间来组装，并且可能需要不时进行自我维修。

#### 在Crowd Supply网站预购官方DIY套件

![DIY kit](assets/img/DIY_KIT_box-contents.jpg)<br>
*A prototype of DIY-Kit boards and wires.*

您可以购买 [**official DIY Kit**](https://www.crowdsupply.com/slimevr/slimevr-full-body-tracker)，其中包括您需要的所有板和电缆，获得LiPo电池，并将电池连接到板上。您只需要自己3D打印（或构建）一个漂亮的外壳并获得绑带（或创意地用电气胶带将其粘在身上）。有关如何构建它的更多信息，请参见 [DIY Kit Guide](/diy_kit_guide.html) 。

此选项不需要或很少需要焊接，提供经过测试的板、最佳的IMU，允许小型设计，并且是购买完成的SlimeVR追踪器的更便宜的替代品。它还允许您自定义外壳和绑带。

但是，此时您可以直接购买完成的SlimeVR追踪器，因为运输时间和芯片短缺仍然影响此选项。

此选项是预订。请查看产品页面以获取新订单的预计发货时间。实际发货时间可能因生产延误和其他情况而有所不同。

### 3. 备选追踪器方案

由于SlimeVR是开源的，并且根植于实验和探索的思想，因此已经构建了其他替代自定义构建追踪器的选项。这包括：

- 使用 [手机作为追踪器](tools/owoTrack.md).
- 使用 [任天堂Joycons手柄作为追踪器](tools/slimevr-wrangler.html).

**请注意，与追踪器相比，这两个选项都不够好，但对于实验非常有用。我们建议您不要大量投资购买旧手机或Joycons，因为这些选项的大多数用户最多只考虑它们是临时措施。**

请注意，这些选项因制造和型号而异（例如，第三方joycons几乎从不起作用），存在连接问题、应用程序被暂停以及其他一些问题。还需要根据对象的形状、大小和安装位置来获取手机或Joycon绑带。

如果您有任何问题，请随时在[SlimeVR discord](https://discord.gg/SlimeVR)上联系我们。

*Written by adigyran#1121 and CalliePepper#0666, edited by QuantumRed#0001, CalliePepper#0666, Spazzwan Emojikage#3095, NWB#5135, and Tom Yum#0069, styled by CalliePepper#0666*
*中文本地化：DazaiYuki*
