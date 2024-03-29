# Project 14 : Mini Table Lamp

1.  **Introduction**

Did you know that a Raspberry Pi Pico can light up an LED when you press a button? In this project, we will use the Raspberry Pi Pico, a key switch and an LED to make a Mini Table lamp.

2.  **Components Required**

<table>
<tbody>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/222aee34a428755aaf97b711ded3f09a.jpeg" style="width:2.01667in;height:0.80278in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/bbed91c0b45fcafc7e7163bfeabf68f9.png" style="width:1.67014in;height:1.28472in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/5b8fea4657b47510d199f740fdcaaa9d.png" style="width:1.06736in;height:0.74236in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/ef77f5a64c382157fc2dea21ec373fef.png" style="width:0.29514in;height:1.25903in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/da8a2a9d15baf7280966f3fdbb025a8c.png" style="width:0.26042in;height:1.16667in" /></td>
</tr>
<tr class="even">
<td>Raspberry Pi Pico*1</td>
<td>Raspberry Pi Pico Expansion Board*1</td>
<td>Button*1</td>
<td>Red LED*1</td>
<td>10KΩResistor*1</td>
</tr>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/e380dd26e4825be9a768973802a55fe6.png" style="width:0.59028in;height:1.44583in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/845d05a6108b1662b828610ba9dcb788.png" style="width:0.25833in;height:1.13681in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/7dcbd02995be3c142b2f97df7f7c03ce.png" style="width:1.05903in;height:0.56667in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/e9a8d050105397bb183512fb4ffdd2f6.png" style="width:0.8375in;height:0.83194in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/9cab81f7da18c7b0c245ec2a2f614f3a.png" style="width:0.84514in;height:0.83264in" /></td>
</tr>
<tr class="even">
<td>Breadboard*1</td>
<td>220ΩResistor*1</td>
<td>USB Cable*1</td>
<td><p>Jumper</p>
<p>Wires</p></td>
<td>Button Cap*1</td>
</tr>
</tbody>
</table>

3.  **Component Knowledge**

![](/media/5b8fea4657b47510d199f740fdcaaa9d.png)

**Button:** The button can control the circuit on and off. The circuit is disconnected when the button is not pressed. But it breaks when you release it. Why does it only work when you press it? It starts from the internal structure of the button, which is shown in the figure:![](/media/d2a204e61c768f18924150db58aee093.png). Before the button is pressed, 1 and 2 are on, 3 and 4 are also on, but 1, 3 or 1, 4 or 2, 3 or 2, 4 are off(not working). Only when the button is pressed, 1, 3 or 1, 4 or 2, 3 or 2, 4 are on. The key switch is one of the most commonly used components in circuit design.

**Schematic diagram of the button:**

![](/media/5e42fde9876f9be810d85a7fb8b331f7.png)
![](/media/8677548f9e756281629430d66ba3a460.png)

**What is button jitter?**

We think of the switch circuit as "press the button and turn it on immediately", "press it again and turn it off immediately". In fact,
this is not the case.

The button usually uses a mechanical elastic switch, and the mechanical elastic switch will produce a series of jitter due to the elastic action at the moment when the mechanical contact is opened and closed (usually about 10ms). As a result, the button switch will not immediately and stably turn on the circuit when it is closed, and it will not be completely and instantaneously disconnected when it is turned off.

![](/media/7e7ac82db8bb810a7ee1de4181ceaa2d.jpeg)

**How to eliminate the jitter?**

There are two common methods, namely fix jitter in the software and hardware. We only discuss the jitter removal in the software.

We already know that the jitter time generated by elasticity is about 10ms, and the delay command can be used to delay the execution time of the command to achieve the effect of jitter removal.

Therefore, we delay 0.02s in the code to achieve the key anti-shake function.

![](/media/c0d68d1134b0b4097e8983ed2cac07fc.jpeg)

**4.** **Circuit Diagram and Wiring Diagram**

![](/media/0753a2a452e0292b31f79f9b6dabb0cc.png)

![](/media/a03a6553dc194ab61fb7b4d914740f90.png)

**Note:**

How to connect the LED

![](/media/f70404aa49540fd7aecae944c7c01f83.jpeg)

How to identify the 220Ω 5-band resistor and 10KΩ 5-band resistor

![](/media/55c0199544e9819328f6d5778f10d7d0.png)

![](/media/246cf3885dc837c458a28123885c9f7b.png)

**5.Test Code**

The code used in this project is saved in the file KS3020 Keyestudio Raspberry Pi Pico Learning Kit Ultimate Edition\\3. Raspberry Pi System\\Python\_Tutorial\\2. Projects\\Project 14：Mini Table Lamp.

You can move the code anywhere. We save the code to the pi folder of the Raspberry Pi system. The path: home/pi/2. Projects

![](/media/ae27830403a2f741aa9b725e5324c215.png)

Open“Thonny”, click“This computer”→“home”→“pi”→“2. Projects”→“Project 14：Mini Table Lamp”. And double-click the “Project\_14\_Mini\_Table\_Lamp.py”.

![](/media/275a3c4efc6794dc8fac059a2aa7f9e1.png)

<table>
<tbody>
<tr class="odd">
<td><p>from machine import Pin</p>
<p>import time</p>
<p>led = Pin(19, Pin.OUT) # create LED object from Pin 19,Set Pin 19 to output</p>
<p>button = Pin(22, Pin.IN, Pin.PULL_UP) #Create button object from Pin22,Set GP22 to input</p>
<p>#Customize a function and name it reverseGPIO(),which reverses the output level of the LED</p>
<p>def reverseGPIO():</p>
<p>if led.value():</p>
<p>led.value(0) #Set led turn off</p>
<p>else:</p>
<p>led.value(1) #Set led turn on</p>
<p>try:</p>
<p>while True:</p>
<p>if not button.value():</p>
<p>time.sleep_ms(20)</p>
<p>if not button.value():</p>
<p>reverseGPIO()</p>
<p>while not button.value():</p>
<p>time.sleep_ms(20)</p>
<p>except:</p>
<p>pass</p></td>
</tr>
</tbody>
</table>

6.  **Test Result**
    
Ensure that the Raspberry Pi Pico is connected to the computer，click“![](/media/ec00367ea605788eab454cd176b94c7b.png)Stop/Restart backend”.

![](/media/a85c858067d3c56ab6f35bc4cc631e5d.png)

Click“![](/media/bb4d9305714a178069d277b20e0934b7.png)Run current script”, the code starts executing, we will see that press the button, the LED lights up;  when the button is released, the LED remains lit. Press the button again, the LED goes off;  When the button is released, the LED remains off. Doesn't it look like a little lamp? Click“![](/media/ec00367ea605788eab454cd176b94c7b.png)Stop/Restart backend”to exit the program.

![](/media/4228655348a81a57813174e42b167955.png)
