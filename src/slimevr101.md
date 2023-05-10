# SlimeVR 101

## 什么是SlimeVR?

SlimeVR是一种低成本的VR全身追踪解决方案。它使用正向运动学来构建您的骨架模型，该模型是从每个单独追踪器的旋转计算出来的，您的VR头显和控制器是唯一已知的绝对位置。

<div class="embeddedVideo">
	<video name="Firmware Tools Example" codecs='video/webm;codecs="vp9"' autoplay muted loop>
	  <source src="./assets/videos/ostriches.webm">
	</video><br>
	Gif thanks to Butterscotch. Dance thanks to ToriKari
</div>

由于VR头显是已知位置，而旋转是从中派生出来的，因此它不需要基站或其他形式的附加追踪来模拟您的运动。您的VR头显和控制器内置的手部追踪管理您的肩膀和手臂。SlimeVR使用惯性测量单元（IMU）的数据来确定旋转，使用的IMU数量决定了可用的追踪点数。

## 你需要多少追踪器？

根据你计划在VR中使用的追踪方案，以下是选项：

* 下半身套装（5个IMU）- 您的腰部，腿部，膝盖和脚部都可以被追踪。腰部弯曲或坐下会影响追踪，而您的脚的方向不会被追踪。
* 核心套装（6个IMU）- 除了上一个套装外，这还在胸部添加了一个追踪器，这样即使您躺下，坐下或弯曲身体也可以进行更准确的追踪。
* 增强核心套装（8个IMU）- 除了上一个套装外，您现在还可以摇动您的双脚。如果您计划经常躺下或坐下，这能够增加捕捉细节。
* 全身套装（10个IMU）- 除了上一个套装外，您现在可以在VR中独立于控制器移动肘部。对于舞者或增加沉浸感非常有用。

如果您查看上面的GIF，则每行都表示追踪的“骨头”。添加更多旋转点会使最终追踪更加清晰。例如，上面的GIF仅具有“核心套装”，因此没有足部旋转。

有关这些追踪选项的更多信息，请参见此视频：

<div class="video-container">
<iframe width="100%" height="auto" src="https://www.youtube.com/embed/KN3dxGNAq34" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay muted; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>


## 什么是扩展?

扩展是附加到主追踪器并放置在另一个位置的单个辅助IMU。这样可以构建一个二级追踪器，而无需额外的电池、充电板或微控制器。这些有时被称为AUX追踪器。扩展允许追踪器在两个靠近的弯曲点之间提供准确的细节，例如同时追踪小腿和脚，而无需另一个需要单独通信或充电的追踪器。

![Extension Image](assets/img/extension.png)<br>
*Example extension built by Rames The Generic#3540*

扩展的长度取决于用于连接它们的电缆（小于80cm是安全范围）。有关更多信息，请 [查看追踪器原理图页面。](diy/tracker-schematics.md)

以下是建议的扩展位置:

1. 附加到腰部追踪器的胸部扩展。
1. 附加到左脚踝追踪器的左脚扩展。
1. 附加到右脚踝追踪器的右脚扩展。

在Crowd Supply商店页面和他们的Discord服务器上，您可以找到指定主要和辅助IMU数量的注释，带有加号。例如，上面提到的增强核心套件将被称为5+3设置，其中包括5个微控制器和8个IMU。为了更好地了解它在人身上的外观，请查看服务器设置的推荐安装点部分。[Recommended mounting points section of the server set up](server/putting-on-trackers.md#recommended-mounting-points).

请注意：如果您愿意，不需要构建扩展，因为如果您愿意，足部和胸部追踪器将作为独立追踪器工作。但是，这些文档假定您正在将它们构建为扩展。

*Created by CalliePepper#0666. Edited by Spazzwan#0001. Video created by ZRock35#9574*
