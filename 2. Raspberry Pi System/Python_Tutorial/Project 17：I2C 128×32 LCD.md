# Project 17： I2C 128×32 LCD

1.  **Introduction**
    
We can use modules such as monitors to do various experiments in life. You can also DIY a variety of small objects. For example, you can make a temperature meter with a temperature sensor and display, or make a distance meter with an ultrasonic module and display.
    
In this project, we will use the LCD\_128X32\_DOT module as a display and connect it to a Raspberry Pi Pico, which will be used to control the LCD\_128X32\_DOT display to show various English characters, common symbols and numbers.
    
2.  **Components Required**

<table>
<tbody>
<tr class="odd">
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/b1265f71184b5d144248ea3e847a18c9.jpeg" style="width:1.75486in;height:0.69861in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/2c2645e94a00867ac23e8a022f0a631a.png" style="width:1.59236in;height:0.76736in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/bb8cfe198d6a21b2dcaa7965992c76c4.png" style="width:0.97569in;height:0.82431in" /></td>
<td><img src="https://raw.githubusercontent.com/keyestudio/KS3020-KS3020F-Keyestudio-Raspberry-Pi-Pico-Ultimate-Starter-Kit-Raspberry-Pi/master/media/7dcbd02995be3c142b2f97df7f7c03ce.png" style="width:1.275in;height:0.68264in" /></td>
</tr>
<tr class="even">
<td>Raspberry Pi Pico*1</td>
<td>LCD_128X32_DOT*1</td>
<td>10CM M-F Dupont Wires</td>
<td>USB Cable*1</td>
</tr>
</tbody>
</table>

3.  **Component Knowledge**
    
![](/media/2c2645e94a00867ac23e8a022f0a631a.png)

**LCD\_128X32\_DOT:** It is an LCD module with 128\*32 pixels and its driver chip is ST7567A. The module uses the IIC communication mode, while the code contains a library of all alphabets and common symbols that can be called directly. When using, we can also set it in the code so that the English letters and symbols show different text sizes. To make it easy to set up the pattern display, we also provide a mold capture software that converts a specific pattern into control code and then copies it directly into the test code for use.

**Schematic diagram:**

![](/media/5451aed32bc5b7b30fbd5613ad09a65b.png)

**Features:**

Pixel：128\*32 character

Operating voltage(chip)：4.5V to 5.5V

Operating current：100mA (5.0V)

Optimal operating voltage(module):5.0V

4.  **Circuit Diagram and Wiring Diagram**
    
Note: The LCD\_128X32\_DOT must be connected with 10CM M-F Dupont wires, which can make the LCD\_128X32\_DOT display
normally. Otherwise, using 20CM M-F Dupont wires may cause the LCD\_128X32\_DOT display abnormally.  

![](/media/82aae0a70e5628c53d7f81f7730cf79a.png)

5.  **Test Code**

The code used in this project is saved in the file KS3020 Keyestudio Raspberry Pi Pico Learning Kit Ultimate Edition\\3. Raspberry Pi System\\Python\_Tutorial\\2. Projects\\Project 17：I2C 128×32 LCD.

You can move the code anywhere. We save the code to the pi folder of the Raspberry Pi system. The path:home/pi/2. Projects

![](/media/ae27830403a2f741aa9b725e5324c215.png)

Open“Thonny”, click“This computer”→“home”→“pi”→“2. Projects”→“Project 17： I2C 128×32 LCD”. Select “lcd128\_32.py”and“lcd128\_32\_fonts.py”，right-click and select“Upload to /”，wait for the“lcd128\_32.py”and the “lcd128\_32\_fonts.py”to be uploaded to the Raspberry Pi Pico. And double--click the“Project\_17\_I2C\_128\_32\_LCD.py”.

![](/media/cf6da403bb3a70da064a800abfcdf3e8.png)

![](/media/34cb4f230ecef649b2c7282576cff27c.png)

![](/media/d6d36ab4b42ff3bcf4b354c8adabf90e.png)

<table>
<tbody>
<tr class="odd">
<td><p>import machine</p>
<p>import time</p>
<p>import lcd128_32_fonts</p>
<p>from lcd128_32 import lcd128_32</p>
<p>#i2c config</p>
<p>clock_pin = 21</p>
<p>data_pin = 20</p>
<p>bus = 0</p>
<p>i2c_addr = 0x3f</p>
<p>use_i2c = True</p>
<p>def scan_for_devices():</p>
<p>    i2c = machine.I2C(bus,sda=machine.Pin(data_pin),scl=machine.Pin(clock_pin))</p>
<p>    devices = i2c.scan()</p>
<p>    if devices:</p>
<p>        for d in devices:</p>
<p>            print(hex(d))</p>
<p>    else:</p>
<p>        print('no i2c devices')</p>
<p>if use_i2c:</p>
<p>    scan_for_devices()</p>
<p>    lcd = lcd128_32(data_pin, clock_pin, bus, i2c_addr)</p>
<p>lcd.Clear()</p>
<p>lcd.Cursor(0, 4)</p>
<p>lcd.Display("KEYESTUDIO")</p>
<p>lcd.Cursor(1, 0)</p>
<p>lcd.Display("ABCDEFGHIJKLMNOPQR")</p>
<p>lcd.Cursor(2, 0)</p>
<p>lcd.Display("123456789+-*/&lt;&gt;=$@")</p>
<p>lcd.Cursor(3, 0)</p>
<p>lcd.Display("%^&amp;(){}:;'|?,.~\\[]")</p>
<p>"""</p>
<p>while True:</p>
<p>    scan_for_devices()</p>
<p>    time.sleep(0.5)</p>
<p>"""</p></td>
</tr>
</tbody>
</table>

6.  **Test Result**
    
Ensure that the Raspberry Pi Pico is connected to the computer，click“![](/media/ec00367ea605788eab454cd176b94c7b.png)Stop/Restart backend”.

![](/media/e47d31acdd5429afcd63acfb0fd0a039.png)

Click “![](/media/bb4d9305714a178069d277b20e0934b7.png)Run current script”, the code starts executing, we will see that the LCD module display will show "KEYESTUDIO" at the first line. "ABCDEFGHIJKLMNOPQR" will be displayed at the second line. "123456789 + - \* / \<\> = $ @ " will be shown at the third line and "% ^ & () {} :; '|?,. \~ \\\\ \[\] " will be displayed at the fourth line. 

Press“Ctrl+C”or click“![](/media/ec00367ea605788eab454cd176b94c7b.png)Stop/Restart backend”to exit the program.

![](/media/ffc4f1df389a52a9b016f4fae9a7b703.png)
