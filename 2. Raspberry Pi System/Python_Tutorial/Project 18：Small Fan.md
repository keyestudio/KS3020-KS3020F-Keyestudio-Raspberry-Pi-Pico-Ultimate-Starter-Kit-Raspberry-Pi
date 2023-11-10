# Project 18：Small Fan

1.  **Introduction**

In the hot summer, we need an electric fan to cool us down, so in this project, we will use a Raspberry Pi Pico to control 130 motor module and small blade to make a small fan.

2.  **Components Required**

<table>
<tbody>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/b18fe281156b29c44796f72222718d58.jpeg" style="width:2.37431in;height:0.94514in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/bbed91c0b45fcafc7e7163bfeabf68f9.png" style="width:1.67014in;height:1.28472in" /></td>
<td></td>
</tr>
<tr class="even">
<td>Raspberry Pi Pico*1</td>
<td>Raspberry Pi Pico Expansion Board*1</td>
<td></td>
</tr>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/a572bcde7a5e3bf01d273b3d9a024701.png" style="width:1.22222in;height:1.10903in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/70ceedcda00dab3b484e5eddbd0382de.png" style="width:1.43611in;height:1.21319in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/7dcbd02995be3c142b2f97df7f7c03ce.png" style="width:1.05903in;height:0.56667in" /></td>
</tr>
<tr class="even">
<td>130 Motor Module*1</td>
<td>M-F Dupont Wires</td>
<td>USB Cable*1</td>
</tr>
</tbody>
</table>

3.  **Component Knowledge**

![](/media/a572bcde7a5e3bf01d273b3d9a024701.png)

130 motor module: The motor control module uses the HR1124S motor control chip, which is a single-channel H-bridge driver chip for DC motor. The H-bridge driving part of the HR1124S features low on-resistance PMOS and NMOS power tube. The low on-resistance ensures low power loss of the chip, making the chip work safely for a longer time. In addition, HR1124S has low standby current and low quiescent current, which makes HR1124S easy to be used in toy scheme.

Features:

Working voltage: 5V

Working current: 200MA

Working power: 2W

Working temperature: -10℃\~ +50℃

**Schematic diagram:**

![](/media/ee2deb2ed7ae310b953ff178aff3d6c1.emf)

4.  **Circuit Diagram and Wiring Diagram**

![](/media/98c9335e5ef2e5304e2cddde04e6e168.png)

![](/media/aad9f071a4d7a6a9a62c2899c78822b8.png)

5.  **Test Code**

The code used in this project is saved in the file S3020 Keyestudio Raspberry Pi Pico Learning Kit Ultimate Edition\\3. Raspberry Pi
System\\Python\_Tutorial\\2. Projects\\Project 18：Small Fan.

You can move the code anywhere. We save the code to the pi folder of the Raspberry Pi system. The path:home/pi/2. Projects

![](/media/ae27830403a2f741aa9b725e5324c215.png)

Open“Thonny”, click““This computer”→“home”→“pi”→“2. Projects”→“Project 18: Small Fan”. And double-click the“Project\_18\_ Small\_Fan.py”.

![](/media/3ae6011fd277fd283c51a2edc38f5af6.png)

<table>
<tbody>
<tr class="odd">
<td><p>from machine import Pin</p>
<p>import time</p>
<p>motor1a = Pin(17, Pin.OUT) # create motor1a object from Pin 17, Set Pin 17 to output</p>
<p>motor1b = Pin(16, Pin.OUT) # create motor1b object from Pin 16, Set Pin 16 to output</p>
<p>def forward():</p>
<p>motor1a.high() # Set motor1a high</p>
<p>motor1b.low() # Set motor1b low</p>
<p>def backward():</p>
<p>motor1a.low()</p>
<p>motor1b.high()</p>
<p>def stop():</p>
<p>motor1a.low()</p>
<p>motor1b.low()</p>
<p>def test():</p>
<p>forward() # motor forward</p>
<p>time.sleep(5) #delay</p>
<p>stop() # motor stop</p>
<p>time.sleep(2)</p>
<p>backward()# motor backward</p>
<p>time.sleep(5)</p>
<p>stop()</p>
<p>time.sleep(2)</p>
<p>for i in range(5):</p>
<p>test()</p></td>
</tr>
</tbody>
</table>

6.  **Test Result**
    
Ensure that the Raspberry Pi Pico is connected to the computer，click“![](/media/ec00367ea605788eab454cd176b94c7b.png)Stop/Restart backend”.

![](/media/b8719ff8af67a604c56bb0d2ca526d1b.png)

Click “![](/media/bb4d9305714a178069d277b20e0934b7.png)Run current script”, the code starts executing, we will see that The small fan turns counterclockwise for 5 seconds and stops for 2 seconds, and then turns clockwise for 5 seconds and stops for 2 seconds. Repeat this rule for 5 times and then the small fan stops. Click“![](/media/ec00367ea605788eab454cd176b94c7b.png)Stop/Restart backend”to exit the program.

![](/media/67a1f00e73daef1dc40651d871597b74.png)
