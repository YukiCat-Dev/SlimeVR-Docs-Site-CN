# IMU 比较
社区已经花费了大量工作去研究DIY SlimeVR Trackers的IMU.
为了更清楚地了解当前可用的IMU的状况，DIY社区进行了一项调查。
这个页面是基于用户反馈和调查结果，分数是取平均数得出的。
模块有很多变数因此仅供参考，查看以前的报告可以点 [SlimeVR Experience Survey page](../misc/survey.md).

## 导航
- [BNO085](#bno085)
- [BMI160](#bmi160)
- [ICM20948](#icm20948)
- [MPU9250](#mpu9250)
- [MPU+QMC5883L](#mpuqmc5883l)
- [BNO055](#bno055)
- [MPU6500](#mpu6500)
- [MPU6050](#mpu6050)
- [Addendum](#addendum)

## 评分标准
我们根据以下几个方面对这些芯片进行排名：校准时间、成本、供应状况和制造质量。
这些因素旨在给出一个快速的指示，让你从各个IMU中取舍，至于具体实际情况可能受到很多方面的影响（店家、制造商、物流……）。
注：如果10个芯片中有3个在到货或早期使用时挂掉，那就是制造质量差。
这里的校准时间是指IMU传感器的复位时间，即在出现漂移或误差时，需要重新校准IMU传感器的时间。时间越长，表示IMU传感器的稳定性越好，越不容易出现漂移或误差。时间越短，表示IMU传感器的稳定性越差，越容易出现漂移或误差。

## 最高性价比
目前，BMI160是最佳的性价比选择，远远超过了其他例如MPU6050这类IMU。因为BMI160不需要稳定的磁场环境，使它成为比9DOF IMU（MPU9250或ICM20948这类）更适合大众，甚至比MPU6050+QMC5883L的方案更好。BNO085虽然综合体验很好但也贵。（注：原文的角度是在欧美，中国境内网购并不需要那么高额的运费）

在参考本页面上IMU的顺序时，请记住，它们是按照从好到坏的顺序大致列出的。

---
## BNO085
这也是SlimeVR官方方案使用的传感器
可靠和稳定的芯片，但很难以适中的价格购买到。


|校准时间 |成本  |可用性|制造质量|
|:---------:|:---:|:----------:|:-----------:|
|30 - 45 min|~$25 |充足  |优秀    |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-half-o"></i>

|优点          |缺点                                   |
|--------------|---------------------------------------|
|精准          |很贵                              |
|可靠         |与MPU系列对比需要额外布线            |
|平滑        |                                       |

---
## BMI160
DIY SlimeVR的主流之一。
BMI160是一款相对较新的芯片，具有不错的性能和良好的可靠性。
建议你使用实验性的固件，因为它可以显著提高BMI160的性能。

|校准时间 |成本  |可用性|制造质量|
|:---------:|:----:|:----------:|:-----------:|
|10 - 20min |~$1.42|充足  |好         |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-half-o"></i><i class="fa fa-star-o" ></i>

|优点                   |缺点                                             |
|-----------------------|-------------------------------------------------|
|便宜                   | 第一次需要手动校准                               |
|可靠                   | 需要实验性固件提供更好的性能                      |
|平滑                   |                                                 |
|单次校准               |                                                 |

---
## ICM20948
ICM 20948是一款相对较新的芯片。
虽然初步测试看起来不错，但这款芯片还没有足够的实地使用时间来得出结论。

ICM-20948有很多种，其中大多数工作在3.3v。
Pimoroni ICM-20948（请注意，这块板子需要你切断背面的桥接，以改变地址）
Adafruit ICM-20948（请注意，这块板子需要你在背面焊接桥接，以改变地址）
SparkFun ICM-20948（请注意，这块板子需要你在背面焊接桥接，以改变地址）
GY-912（请注意，这块板子需要你将SD0和GND桥接，以改变地址）

CJMCU-20948已知运行在1.8v，需要额外的硬件才能工作。
需要一个1.8v线性电压调节器和逻辑电平转换器，因此不推荐使用这块板子。



|校准时间 |成本  |供应状况|制造质量|
|:---------:|:---:|:----------:|:-----------:|
|15 - 60 min|~$15 |不足 |Good         |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-half-o"></i>

|Pros             |Cons                                 |
|-----------------|-------------------------------------|
|Accurate         |Currently still in testing           |
|Reliable         |Sensitive to bad magnetic enviroments|
|Smooth           |Availability is not guaranteed       |

`Comment: Prone to some drift when moving really fast (in 6DoF mode).`

---
## MPU9250
The MPU9250 (currently ran in several modes) is a newer installment of the MPU lineup.

|Reset time |Cost |Availability|Build quality|
|:---------:|:---:|:----------:|:-----------:|
|10 - 40 min|~$7  |Insufficient|Mediocre     |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-o" ></i><i class="fa fa-star-o" ></i>

|Pros             |Cons                                             |
|-----------------|-------------------------------------------------|
|Affordable       |Very prone to counterfeit/DOA units              |
|Smooth           |Sensitive to bad magnetic enviroments            |
|Reliable         |Requires manual calibration the first time       |

`Comment: Finding legitimate MPU9250s has become exceedingly difficult due to counterfeits and DOA IMUs. Buy at your own risk.`

---
## MPU+QMC5883L
This is a highly experimental setup that approximately matches an MPU9250.
Unlike other IMUs which consist of a single PCB, this instead relies on connecting a magnetometer to an MPU6050 or MPU6500.
That being said, a breakout board which includes both an MPU6050 and an HMC5883L does exist: the GY-87.
Both the QMC5883L and HMC5883L may be used, however, the QMC5883L may potentially perform better.


|Reset time |Cost  |Availability|Build quality|
|:---------:|:----:|:----------:|:-----------:|
|10 - 40min |~$2.50|Sufficient  |Mixed        |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-half-o"></i><i class="fa fa-star-o" ></i><i class="fa fa-star-o" ></i>

|Pros             |Cons                                             |
|-----------------|-------------------------------------------------|
|Cheap            |Very experimental                                |
|Smooth           |Requires manual calibration the first time       |
|Reliable         |Sensitive to bad magnetic enviroments            |
|                 |Complex wiring                                   |

`Comment: Requires experimental firmware.`

---
## BNO055
Earlier version of the BNO085 without stabilisation firmware.

*This chip does not have sufficient test results for a conclusive summary.*

|Reset time |Cost |Availability|Build quality|
|:---------:|:---:|:----------:|:-----------:|
|1 -10 min  |~$55 |Mediocre    |Good         |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-half-o"></i><i class="fa fa-star-o" ></i><i class="fa fa-star-o" ></i>

|Pros                           |Cons                                          |
|-------------------------------|----------------------------------------------|
|Build Quality                  |Expensive                                     |
|Available                      |Can supposedly lose tracking with rapid motion|
|Smooth                         |Insufficient testing                          |

`Comment: Insufficient testing for a accurate description, but cannot compete with BNO085.`

---
## MPU6500
The MPU6500 is the middle ground of the MPU chips available.
The drift time of this IMU may be a slight improvement over the MPU6050.

|Reset time |Cost |Availability|Build quality|
|:---------:|:---:|:----------:|:-----------:|
|5 - 10 min |~$1  |Sufficient  |Mediocre     |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-o" ></i><i class="fa fa-star-o" ></i>

|Pros             |Cons                                    |
|-----------------|----------------------------------------|
|Affordable       |High drift rate                         |
|Available        |More expensive than the 6050 counterpart|
|Smooth           |Failure rate inconsistent               |
|                 |Calibration on each start               |

`Comment: Tracking slightly better than the MPU6050.`

---
## MPU6050
The MPU6050 will get you started with SlimeVR for cheap.

|Reset time |Cost  |Availability|Build quality|
|:---------:|:----:|:----------:|:-----------:|
|1 - 5 min  |~$1.04|Sufficient  |Poor         |

Score: <i class="fa fa-star"></i><i class="fa fa-star"></i><i class="fa fa-star-half-o"></i><i class="fa fa-star-o"></i><i class="fa fa-star-o" ></i>

|Pros             |Cons                      |
|-----------------|--------------------------|
|Cheap            |High drift rate           |
|High availability|High failure rate         |
|                 |Calibration on each start |

`Comment: Order more than you need because of the higher failure rate, it is not uncommon to find 2 to 3 bad chips in a batch.`

---
# Addendum

## What's the difference between an IMU with a magnetometer (9 DOF) and an IMU without a magnetometer (6 DOF)?

IMUs with a magnetometer work like a compass and use the Earths magnetic field as a reference point to eliminate gyroscope drift, however they require a stable magnetic environment or else they will perform erratically. IMUs without a magnetometer don't require a stable magnetic environment, but are prone to gyroscope drift over time due to being unable to differentiate sensor noise from actual movement and so will slowly spin in the yaw axis over time. For SlimeVR's purposes neither is implicitly better or worse than the other. The BNO085, which is the IMU official SlimeVR trackers will use, is used in 6DOF mode and yet performs the best out of all supported IMUs, for example.

## How can I check if I have an acceptable magnetic environment?

You can check by downloading any magnetometer app that shows what your magnetic field strength is in uT and by walking around your playspace. You may want to check at varying heights, such as at chest level, waist level, and ankle level. An option available on both iOS and Android is the app, Physics Toolbox Magnetometer. If you do use Physics Toolbox Magnetometer, you only need to pay attention to the **total**, not the X, Y, or Z components. Most phones have a magnetometer, but if yours does not, then there is no way to be exactly sure of your magnetic environment, but you can make some educated assumptions.

## My app show around X uT is that okay?

There's no one value that's acceptable. What matters is that the range of values is low. There is currently limited data to give an exact range, but a good baseline seems to be a range of less than or equal to 5 uT. For example, 20-25 uT would be okay as would 40-45 uT, but a range from 20-40 uT would likely be too unstable to use.

## What determines a "poor magnetic environment"?

Often things made of steel or other ferromagnetic materials contribute most to a poor magnetic environment. Some common examples of things that might affect your magnetic environment include, but are not limited to: spring mattresses, radiators, PC cases, desktop speakers, or furniture that's made of steel. In most cases, the effect that these things will have extend about 6-12 inches (15-30 cm) and within that range may cause the IMU to rotate incorrectly. The size and amount of mass directly impacts the size of the effected area; a paper clip might only affect your IMU if it's directly next to it, whereas a steel bedframe might affect an area 6-12 inches (15-30 cm) away as previous mentioned. In most cases, depending on the size of your playspace, these issues of certain objects causing interference can be mitigated by avoiding or reposition them. Regardless, other factors such as the wiring or rebar in your building could also affect your magnetic environment. These last few examples are harder to predict and illustrate why it's important to test with an app before assuming you might have a stable magnetic environment.

It's also worth mentioning that some controllers have magnets in them, either to hold the battery door closed or for the trigger. As such, placing your controller near a tracker with a magnetometer may cause it to spin slightly.

## Does magnetic interference cause drift?

No, but you may still need to reset. When in an area of magnetic interference an IMU with a magnetometer will reorient itself the same way a compass will when put near a magnet; if you take the magnet away from the compass, the compass will return pointing towards magnetic North. As mentioned though, you may still find yourself needing to reset. For instance, if your bed has a steel bedframe you'll likely need to perform a reset so that your trackers are facing the correct direction. If you then move somewhere else within your playspace you'll likely then need to reset once again.

## Can I still use my IMU with a magnetometer if I don't have a stable magnetic environment?

This cannot be recommended. When run without the magnetometer, IMUs with magnetometers such as the MPU9250 and ICM20948, perform much worse. That said, if for whatever reason you do want to use your IMU without the magnetometer, the MPU6500 or MPU6050 firmware can be used on the MPU9250 instead, and the ICM20948 can run in 6DOF mode.

## IMU Calibration

Some IMUs, such as the MPU9250, BMI160, and MPU+QMC5883L, require manual calibration. This only needs to be performed once upon first setting up your SlimeVR tracker, however, you may need to perform the calibration multiple times before reaching satisfactory results. More information on how you would calibrate your IMUs can be [found here.](../server/initial-setup.md#imu-calibration)

---
### Credits
*Created by Smeltie#1999, edited by #calliePepper#0666 and NWB#5135*

A big thanks to everyone who took the time to fill out the survey.
