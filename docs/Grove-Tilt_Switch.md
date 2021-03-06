---
title: Grove - Tilt Switch
category: Sensor
bzurl: https://seeedstudio.com/Grove-Tilt-Switch-p-771.html
oldwikiname: Grove_-_Tilt_Switch
prodimagename: Tilt1.jpg
bzprodimageurl: http://statics3.seeedstudio.com/images/product/gbtlt.jpg
surveyurl: https://www.research.net/r/Grove-Tilt_Switch
sku: 101020025
tags: grove_digital, io_3v3, io_5v, plat_duino, plat_pi, plat_bbg
---

![](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/img/Tilt1.jpg)

The Grove-Tilt Switch is the equivalent of a button, and is used as a digital input. Inside the tilt switch is a pair of balls that make contact with the pins when the case is upright. Tilt the case over and the balls don't touch, thus not making a connection. It is wired to the SIG line, NC is not used on this Grove.

[![](https://raw.githubusercontent.com/SeeedDocument/common/master/Get_One_Now_Banner.png)](https://www.seeedstudio.com/Grove-Tilt-Switch-p-771.html)

Features
--------

-   Grove Interface
-   Easy to use
-   Simple Grove module

!!!Tip
    More details about Grove modules please refer to [Grove System](http://wiki.seeedstudio.com/Grove_System/)
    
Specifications
--------------

<table border="1" cellspacing="0" width="80%">
<tr>
<th scope="col">
Item
</th>
<th scope="col">
Min
</th>
<th scope="col">
Typical
</th>
<th scope="col">
Max
</th>
<th scope="col">
Unit
</th>
</tr>
<tr align="center">
<th scope="row">
Voltage
</th>
<td>
4.75
</td>
<td>
5.0
</td>
<td>
5.25
</td>
<td>
V
</td>
</tr>
<tr align="center">
<th scope="row">
Connecting Angle
</th>
<td colspan="3">
10° ~170°
</td>
<td>
-
</td>
</tr>
<tr align="center">
<th scope="row">
Disconnect angle
</th>
<td colspan="3">
190° ~350°
</td>
<td>
-
</td>
</tr>
<tr align="center">
<th scope="row">
Electrical Life
</th>
<td colspan="3">
100,000
</td>
<td>
Cycle
</td>
</tr>
</table>

Platforms Supported
-------------------

| Arduino                                                                                             | Raspberry Pi                                                                                             | BeagleBone                                                                                      | Wio                                                                                               | LinkIt ONE                                                                                         |
|-----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|
| ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/arduino_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/raspberry_pi_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/bbg_logo.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/wio_logo_n.jpg) | ![](https://raw.githubusercontent.com/SeeedDocument/wiki_english/master/docs/images/linkit_logo_n.jpg) |

!!!Caution
    The platforms mentioned above as supported is/are an indication of the module's hardware or theoritical compatibility. We only provide software library or code examples for Arduino platform in most cases. It is not possible to provide software library / demo code for all possible MCU platforms. Hence, users have to write their own software library.


Usage
-----

### With Arduino

The SIG pin of the Grove - Tilt Switch output LOW normally. When the Tilt Switch is upright, a pair of balls inside the tilt switch will contact with the pins and the SIG pin will output HIGH.

The following sketch demonstrates a simple application of using the Tilt Switch and Grove - Button to control the led.

-   As the following picture indicates, the Tilt Switch is connected to digital port 5 of the Grove - Base Shield and the Grove-Button to digital port 7. The LED is connected to digital port 1. The hardware installation is as follows:

![](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/img/Digitalv1.0b.jpg)

-   Copy and paste code below to a new Arduino sketch.

```
void setup()
{
    pinMode(1, OUTPUT);
    pinMode(5, INPUT);
    pinMode(7, INPUT);
}

void loop()
{

    if (digitalRead(5)==HIGH)
    {
        digitalWrite(1, HIGH);
        delay(100);
        digitalWrite(1, LOW);
    }

    if (digitalRead(7)==HIGH)
    {
        digitalWrite(1, HIGH);
        delay(200);
        digitalWrite(1, LOW);
    }

}
```

-   Upload the code.
-   Then the LED will light when you press the button or activate the tilt-switch. Have a try!

Reference
---------

The operating angle of Grove-Tilt Switch as shown below:

![](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/img/Tilt_Switch_Operate.jpg)

<div class="admonition note">
<p class="admonition-title">Note</p>
The mark J1 on the Grove is the reference terminal.
</div>

### With Raspberry Pi

1.You should have a Raspberry Pi and a Grovepi or Grovepi+. 

2.You should have completed configuring the development enviroment, otherwise follow [here](/GrovePiPlus).

3.Connection

-   Plug Tilt_Switch into grovepi socket D3 by using a grove cable.

4.Navigate to the demos' directory:
```
       cd yourpath/GrovePi/Software/Python/
```
-   To see the code
```
    nano grovepi_tilt_switch.py   # "Ctrl+x" to exit #
```
```
    import time
    import grovepi

    # Connect the Grove Tilt Switch to digital port D3
    # SIG,NC,VCC,GND
    tilt_switch = 3

    grovepi.pinMode(tilt_switch,"INPUT")

    while True:
        try:
            print grovepi.digitalRead(tilt_switch)
            time.sleep(.5)

        except IOError:
            print "Error"
```

5.Run the demo.
```
    sudo python grove_tilt_switch.py
```

6.Result: Put the sensor upright by one side, the SIG pin will output HIGH.

![](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/img/Grovepi_tilt_Switch_00.png)

Resources
---------

-   [Grove - Tilt Switch v1.0 Eagle File](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/res/Grove-Tilt_Switch_v1.0_Source_File.zip)
-   [Grove - Tilt Switch v1.1 PDF File](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/res/Grove-Tilt_Switch_v1.1_PDF_File.pdf)
-   [Grove - Tilt Switch v1.1 Eagle File](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/res/Grove-Tilt_Switch_v1.1_Eagle_File.zip)
-   [SW200D Datasheet](https://raw.githubusercontent.com/SeeedDocument/Grove-Tilt_Switch/master/res/SW200D_datasheet.pdf)


<!-- This Markdown file was created from http://www.seeedstudio.com/wiki/Grove_-_Tilt_Switch -->

## Tech Support
Please do not hesitate to contact [techsupport@seeed.cc](techsupport@seeed.cc) if you have any technical issue. Or submit the issue into our [forum](http://seeedstudio.com/forum/). 