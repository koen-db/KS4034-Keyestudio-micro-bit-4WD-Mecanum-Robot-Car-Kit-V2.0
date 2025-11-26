## Assemble Mecanum Robot  

It is a programmable car based on BBC micro:bit. It integrates a motor driver, a line tracking sensor and an IR receiver into the base plate, which also contains an ultrasonic sensor, a servo, 2 seven-color lights as well as 4 WS2812 RGB lights. The wiring is not complicated and it has Lego jacks to facilitate connection with other peripheral devices. Abundant hardware resources will enable you to master more knowledge and skills to create more technological inventions.

## Sensors and control pins of the 4WD Mecanum Robot Car V2.0

This car can help you to better learn how to use the Micro:bit and make electronic knowledge accessible to you.

**Functions**

|        |                   |                       |       |                   |                      |             |                  |              |
| ------ | ----------------- | --------------------- | ----- | ----------------- | -------------------- | ----------- | ---------------- | ------------ |
| Sensor | Seven-color light | Decelerating DC motor | Servo | Ultrasonic sensor | Line Tracking Sensor | IR Receiver | WS2812 RGB light | Power switch |
| QTY    | 2                 | 4                     | 1     | 1                 | 3                    | 1           | 4                | 1            |

**Note: the line tracking sensor, WS2812 RGB lights, IR receiver and moto river are integrated in the base plate.**

**Pins：**

![Img](./media/Pins.png)

**Power supply and Battery**

The keyestudio 4WD Mecanum Robot Car is powered by two 18650 batteries. The battery holder of the car is compatible with any type of 18650 lithium battery (rechargeable). You can use a universal battery charger to charge the 18650 lithium battery.

**Note:** This product does not contain batteries.

## The Installation of Keyestudio 4WD Mecanum Robot Car V2.0 

Step 1

**Components Needed:**

![](./media/b1.png)

**Installation Diagram:**

![](./media/b2.png)

**Prototype:**

![](./media/b3.png)

Step 2

**Components Needed:**

![](./media/b4.png)

**Installation Diagram:**

![](./media/b5.png)

**Prototype:**

![](./media/b6.png)

Step 3

**Components Needed:**

![](./media/b7.png)

**Installation Diagram:**

![](./media/b8.png)

**Prototype:**

![](./media/b9.png)

Step 4

（adjust the angle of the servo first）

**Adjust the angle of the servo to 90 degrees.**

**Method 1：MakeCode code**

⚠️**Special note:** Before you write the code and upload it, you must Understand the MakeCode IDE and add library files, please go to the the link: [Get Started with makecode](./Code1.7z)

![](./media/b10.png)

The MakeCode code above is provided in the materials. Open the adjustment code of the servo and burn it into the microbit motherboard of the 4WD Mecanum Robot Car V2.0, and **power on via micro USB cable or external power supply(turn the DIP switch to ON)**. That's it. The code is at the following position as shown in the figure:

![Img](./media/b11.png)

**Method 2：Python code**

⚠️**Special note:** Before you write the code and upload it, you must install the Mu IDE and add library files, please go to the the link: [Get Started with Python](./Code2.7z)

```Python
# import microbit related libraries
from microbit import *

class Servo:
    def __init__(self, pin, freq=50, min_us=600, max_us=2400, angle=180):
        self.min_us = min_us
        self.max_us = max_us
        self.us = 0
        self.freq = freq
        self.angle = angle
        self.analog_period = 0
        self.pin = pin
        analog_period = round((1/self.freq) * 1000)  # hertz to miliseconds
        self.pin.set_analog_period(analog_period)

    def write_us(self, us):
        us = min(self.max_us, max(self.min_us, us))
        duty = round(us * 1024 * self.freq // 1000000)
        self.pin.write_analog(duty)
        sleep(100)
        self.pin.write_analog(0)

    def write_angle(self, degrees=None):
        if degrees is None:
            degrees = math.degrees(radians)
        degrees = degrees % 360
        total_range = self.max_us - self.min_us
        us = self.min_us + total_range * degrees // self.angle
        self.write_us(us)


Servo(pin14).write_angle(90)
sleep(1000)
```

**Components Needed:**

![](./media/b13.png)

Installation Diagram: (mind the installation direction)

![](./media/b14.png)

**Prototype:**

![](./media/b15.png)

Step 5

**Components Needed:**

![](./media/b16.png)

**Installation Diagram:**

![](./media/b17.png)

**Prototype:**

![](./media/b18.png)

Step 6

**Components Needed:**

![](./media/b19.png)

**Installation Diagram:**

![](./media/b20.png)

**Prototype:**

![](./media/b21.png)

Step 7

**Components Needed:**

![](./media/b22.png)

**Installation Diagram:** (mind the direction of the motor)

![](./media/b23.png)

**Prototype:**

![](./media/b24.png)

Step 8

**Components Needed:**

![](./media/b25.png)

**Installation Diagram:** (Pay attention to the installation direction of the mecanum wheel)

![](./media/b26.png)

**Prototype:**

![](./media/b27.png)

Step 9

**Components Needed:**

![](./media/b28.png)

**Installation Diagram:**

![](./media/b29.png)

**Prototype:**

![](./media/b30.png)

Step 10

**Components Needed:**

![](./media/b31.png)

**Installation Diagram:**

![](./media/b32.png)

**Prototype:**

![](./media/b33.png)

Wiring Diagram

**The wiring of the servo:**

![Img](./media/b34.png)

![](./media/b35.jpg)

![](./media/b36.png)

**The wiring of the ultrasonic sensor:**

![Img](./media/b37.png)

![](./media/b38.jpg)

![](./media/b39.png)

**The wiring of the IR receiver module:**

![Img](./media/b40.png)

![](./media/b41.png)

**The wiring of the RGB:**

![Img](./media/b42.png)

![](./media/b43.jpg)

**The wiring of controlling the motor and seven-color light :**

![Img](./media/b44.png)

![](./media/b45.jpg)

**The wiring of controlling the 3-channel line-tracking sensor:**

![Img](./media/b46.png)

![](./media/b47.jpg)

**The wiring of the power supply:**

![](./media/b48.jpg)

**The corresponding interface of the motor:**

![](./media/b40.jpg)

**The installation of the battery:**

![](./media/b50.png)



