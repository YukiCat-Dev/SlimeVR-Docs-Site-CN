# 设置环境

This procedure will show how to prepare your system for uploading the firmware to your tracker.

## 1. 安装 Visual Studio Code

下载 [最新的VS Code](https://code.visualstudio.com/download)然后安装。

<div class="embeddedVideo">
	<video name="Downloading Visual Studio Code" codecs='video/webm;codecs="vp9"' autoplay muted loop controls>
	  <source src="../assets/videos/downloadVSC.webm">
	</video><br>
	选择正确的环境
</div>

<div class="embeddedVideo">
	<video name="Installing Visual Studio Code" codecs='video/webm;codecs="vp9"' autoplay muted loop controls>
	  <source src="../assets/videos/installVSC.webm">
	</video><br>
	跟随安装进程
</div>

## 2. 安装 PlatformIO IDE

安装完Visual Studio Code后，打开并安装 [PlatformIO IDE for VSCode](https://marketplace.visualstudio.com/items?itemName=platformio.platformio-ide), 扩展，它将允许您连接到追踪器，构建和上传固件。

<div class="embeddedVideo">
	<video name="Installing PlatformIO" codecs='video/webm;codecs="vp9"' autoplay muted loop controls>
	  <source src="../assets/videos/installPIO.webm">
	</video><br>
</div>

## 3. 安装设备驱动

**请注意: 如果你下载并运行SlimeVR Server这些驱动会自动安装.**

### For CH340 (NodeMCU v3, Wemos D1 Mini, and official SlimeVR trackers)

下载 `CH341SER.EXE` 文件从 [这里](https://cdn.sparkfun.com/assets/learn_tutorials/8/4/4/CH341SER.EXE), 跟随安装指引运行。

<div class="embeddedVideo">
	<video name="The Install wizard for CH341SER" codecs='video/webm;codecs="vp9"' autoplay muted loop controls>
	  <source src="../assets/videos/installCH.webm">
	</video><br>
</div>

### For CP210X (NodeMCU v2)

1. 从silicon labs下载驱动的ZIP压缩包 [点这里](https://www.silabs.com/documents/public/software/CP210x_Windows_Drivers.zip).

   如果是其他操作系统可以在 [这里](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)找到.

1. 解压下载的压缩包, 运行 `CP210xVCPInstaller_x64.exe` (`CP210xVCPInstaller_x86.exe` 如果你是32位系统) 然后跟随安装指引。

## 4. 安装Git 客户端

对于Windows用户, 你能下载并安装 [Git for Windows](https://git-scm.com/download/win). 如果你是其他系统，访问 [https://git-scm.com/downloads](https://git-scm.com/downloads).

<div class="embeddedVideo">
	<video name="Installing Git for Windows" codecs='video/webm;codecs="vp9"' autoplay muted loop controls>
	  <source src="../assets/videos/installGit.webm">
	</video><br>
   批注: 你很可能不得不点击 "Click here to download manually". 如果没反应你可以尝试 <a href="https://gitforwindows.org/">这里</a>.
</div>

## 5. Clone the Firmware Project

确保你已经关闭其他项目文件或在跟随下列步骤前打开一个新窗口.

1. 点击 **Source Control** 按钮, 然后点击 **Clone Repository** 并访问: `https://github.com/SlimeVR/SlimeVR-Tracker-ESP.git`. 如果你正在使用 实验性 MPU+QMC5883L 追踪器, 则你需要Clone `https://github.com/deiteris/SlimeVR-Tracker-ESP.git`.

   如果你在Visual Studio Code运行的时候安装Git，你可能需要关掉并重新打开它。

   <div class="embeddedVideo">
      <video name="The Cloning process in VSC" codecs='video/webm;codecs="vp9"' autoplay muted loop controls>
         <source src="../assets/videos/cloneVSC.webm">
      </video><br>
   </div>

1. 当你选好下载路径后点击右下角会出现的 **Open button** .

   ![Clicking the Open Button](../assets/img/openButton.png)

1. 点击 **Yes, I trust the authors**.

   ![Clicking Yes, I trust the authors](../assets/img/pleaseTrust.png)

1. **(MPU+QMC5883L 限定)** 点击 **Source Control** 按钮, 点击 **main** 然后从下拉中选择 **qmc-mag-new** 或 **hmc-mag**， 这取决于你使用的是 QMC5883L 或 HMC5883L.

   <div class="embeddedVideo">
      <video name="Where to find the changes for MPU+QMC5883L" codecs='video/webm;codecs="vp9"' autoplay muted loop controls>
         <source src="../assets/videos/MPUChanges.webm">
      </video><br>
   </div>
