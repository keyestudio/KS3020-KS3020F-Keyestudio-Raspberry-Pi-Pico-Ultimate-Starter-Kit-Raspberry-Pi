# Project 08: 1-Digit Digital Tube

1.  **Introduction**

The seven-segment digital tube is an electronic display device that displays decimal numbers. It is widely used in digital clocks,
electronic meters, basic calculators and other electronic devices that display digital information. The tubes are an alternative to more complex dot-matrix displays that are easy to use in both limited light conditions and strong sunlight. In this project, we will use the Raspberry Pi Pico to control 1-digit digital tube to display numbers.

2.  **Components Required**

<table>
<tbody>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/b18fe281156b29c44796f72222718d58.jpeg" style="width:2.37431in;height:0.94514in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/bbed91c0b45fcafc7e7163bfeabf68f9.png" style="width:1.67014in;height:1.28472in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/75e38d601750a4707369bc73d8028063.png" style="width:0.92361in;height:1.02986in" /></td>
<td></td>
</tr>
<tr class="even">
<td>Raspberry Pi Pico*1</td>
<td>Raspberry Pi Pico Expansion Board*1</td>
<td>1-digit Digital Tube*1</td>
<td></td>
</tr>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/098a2730d0b0a2a4b2079e0fc87fd38b.png" style="width:1.22639in;height:0.49236in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/e380dd26e4825be9a768973802a55fe6.png" style="width:0.50347in;height:1.23333in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/c801a7baee258ff7f5f28ac6e9a7097b.png" style="width:0.66736in;height:0.64097in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/7dcbd02995be3c142b2f97df7f7c03ce.png" style="width:1.05903in;height:0.56667in" /></td>
</tr>
<tr class="even">
<td>220ΩResistor*8</td>
<td>Breadboard*1</td>
<td><p>Breadboard</p>
<p>Wires</p></td>
<td>USB Cable*1</td>
</tr>
</tbody>
</table>

**3. Component Knowledge**

![](/media/e44a0f27beec739ee13e68c04865989f.png)

**Display principle:** The digital tube display is a semiconductor light-emitting device. Its basic unit is a light-emitting diode (LED).
The digital tube display can be divided into 7-segment digital tube and 8-segment digital tube according to the number of segments. The 8-segment digital tube has one more LED unit than the 7-segment digital tube (used for decimal point display). Each segment of the 7-segment LED display is a separate LED. According to the connection mode of the LED unit, the digital tube can be divided into a common anode digital tube and a common cathode digital tube.

In the common cathode 7-segment digital tube, all the cathodes (or negative electrodes) of the segmented LEDs are connected together, so you should connect the common cathode to GND. To light up a segmented LED, you can set its associated pin to “HIGH”.

In the common anode 7-segment digital tube, the LED anodes (positive electrodes) of all segments are connected together, so you should connect the common anode to “+5V”. To light up a segmented LED, you can set its associated pin to “LOW”.

![](/media/28fd057848fbe0e8c8e3362768e7aa44.png)

Each part of the digital tube is composed of an LED. So when you use it, you also need to use a current limiting resistor. Otherwise, the LED will be damaged. In this experiment, we use an ordinary common cathode one-bit digital tube. As we mentioned above, you should connect the common cathode to GND. To light up a segmented LED, you can set its associated pin to “HIGH”.

**4. Circuit Diagram and Wiring Diagram**

![](/media/84e67e0ce2d7627a96b83156324d92d5.png)

**Note:** The direction of the 7-segment digital tube inserted into the breadboard is the same as the wiring diagram, and there is one more point in the lower right corner.

![](/media/66da2f88234019c4a712494174ea4426.png)

![](/media/d99daa4165cf32b2283aae82466981bd.png)

**5. Test Code**

The digital display is divided into 7 segments, and the decimal point display is divided into 1 segment. When certain numbers are displayed, the corresponding segment will be illuminated. For example, when the number 1 is displayed, segments b and c will be opened.

The code used in this project is saved in the file KS3020 Keyestudio Raspberry Pi Pico Learning Kit Ultimate Edition\\3. Raspberry Pi System\\Python\_Tutorial\\2. Projects\\Project 08：1-Digit Digital Tube.

You can move the code to anywhere. For example, we save it in the oi folder of the Raspberry Pi system, the route is home/pi/2. Projects.

![](/media/ae27830403a2f741aa9b725e5324c215.png)

Open“Thonny”, click“This computer”→“home”→“pi”→“2. Projects”→”Project 08：1-Digit Digital Tube”and double-click “Project\_08\_One\_Digit\_Digital\_Tube.py”.

![](/media/bd6201a70a81db2c1ed338e6c901b0c0.png)

<table>
<tbody>
<tr class="odd">
<td><p>from machine import Pin</p>
<p>import time</p>
<p>a = machine.Pin(17, machine.Pin.OUT)</p>
<p>b = machine.Pin(16, machine.Pin.OUT)</p>
<p>c = machine.Pin(14, machine.Pin.OUT)</p>
<p>d = machine.Pin(13, machine.Pin.OUT)</p>
<p>e = machine.Pin(12, machine.Pin.OUT)</p>
<p>f = machine.Pin(18, machine.Pin.OUT)</p>
<p>g = machine.Pin(19, machine.Pin.OUT)</p>
<p>dp = machine.Pin(15, machine.Pin.OUT)</p>
<p>pins = [machine.Pin(id,machine.Pin.OUT) for id in [17, 16, 14, 13, 12, 18, 19, 15]]</p>
<p>def show(code):</p>
<p>for i in range(0, 8):</p>
<p>pins[i].value(~code &amp; 1)</p>
<p>code = code &gt;&gt; 1</p>
<p>#Select code from 0 to 9</p>
<p>mask_digits = [0xc0, 0xf9, 0xa4, 0xb0, 0x99, 0x92, 0x82, 0xf8,0x80, 0x90]</p>
<p>for code in reversed(mask_digits):</p>
<p>show(code)</p>
<p>time.sleep(1)</p></td>
</tr>
</tbody>
</table>
**6. Test Result：**

Connect the pico board to the Raspberry Pi. Click![](/media/32e03e9d4211e9ef97c1d2b18f05c902.png)to check the Shell

![](/media/e4500855559da9a38a02bfcb915f605d.png)

Click ![](/media/bb4d9305714a178069d277b20e0934b7.png) to run the code. Then we will see that the 1-digit digital tube will display numbers from 9 to 0; click![](/media/32e03e9d4211e9ef97c1d2b18f05c902.png)to exit the program.

![](/media/d43aa47d0a7ea776daa925653ea3511b.png)
