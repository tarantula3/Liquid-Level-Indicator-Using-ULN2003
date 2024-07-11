# Liquid Level Indicator Using ULN2003

[![6r3ponugs64](https://i.imgur.com/pPKiuOv.jpeg)](https://youtu.be/6r3ponugs64)

A water level indicator detects and indicates the level of water in an overhead tank and relays the information back to a control panel to indicate whether the tank has a high or low water level.

In this tutorial, I am going to use the ULN2003 IC to create a simple, inexpensive water level indicator.
Using this circuit you can easily control the wastage of water and electricity.
Watch this video, for detailed step by step instructions on how to build this circuit and to know how this circuit works. Towards the end of the video I will also discuss whether its really worth building this circuit.


Components Required
-------------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhzE_9k0-Qu87IfSBxT_DWhHZPsFbYdXhj3YHuR_HYLnn3tLk9fjbNTPFPN6ljlxMwrUvI0_HSIZreHmnHFkywTsDFx2Fwl8iV8o3H708DdEoDDs8lBYg1TvDZ0yODPFWYDJv_8LQOkTI6PAXxdfSaBi9W84rGA9mv-26-ARupRLGM3vlCDpGyFbpEYe6E/w640-h360/1.png)

For this tutorial we need:
* 1 x ULN2003 IC
* 8 x Different Color LEDs
* 8 x 220Ohm Resistors
* 1 x 100Ohm Resistor
* 1 x Buzzer
* A Long Ribbon Cable, and 
* A Breadboard or a Custom Built PCB 


About The ULN2003 IC
--------------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiaAE8xWclhCLxXbMKj0AFs9WAMF7-Om3y1yZN-Dzz_4lrQI4wQCASDxaEkuNxO-AlrmMeA2psHfGP66bJFziBItKWdUDhd05gbSqSbuyeVxyMNl3i7nLoBYjjAD8a0t-OSzB4vkCB5gLRPUjOeQHk_yL13okKMuvDkMgHGCBc-f7Nr2olqU2Xu_HgfRXM/w640-h360/2.png)

The notch on the top indicates the starting and stopping points of the numberings of the chip. Starting from left to right going counterclockwise this is the Pin number 1 of the IC. 
* On the left hand side Pin 1 to 7 are the Base Inputs.
* On the right hand side Pin 10 to 16 are the Collector Outputs.
* Pin 9 is the Common Cathode node for flyback diodes (required for inductive loads).
* And, Pin 8 is the Common Emitter shared by all channels of the IC. This pin is typically tied to ground.

The UNL2003 IC contains 7 High Voltage, High Current NPN Darlington Transistor Arrays each rated at 50V, 500mA in a 16-pin DIP package. You can connect the IC directly to a digital logic (like Arduino or Raspberry Pi, TTL or 5V CMOS device) without an external dropping resistor. The ULN2003 is known for its high current and high voltage capacity.
The Darlington pairs can be "paralleled" for higher current Output.

To know more about this IC, please check out my "Tutorial No. 51: All About ULN2003 IC", the link is in the description below.


Circuit Diagram
---------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEhRRfP94YlP3os3_6n_Y3QNlvZyKWG_hideeNNIUmvPP1r-A9wwQ_cyzm1-dtN80LKd8TQnrhwWzlBhY1SCFUzmKINXcWZ2sFszCB-GZ78Xb7b0gvdJrX84uJMe2fBR9BU4ZsYskB9tTKxsg4numKRLYavsaFXah6vxEWX-haVP_xj1xzd-YeJXxZ4YX7w/w640-h360/4.png)

The circuit is very simple.

I have connected 7 LEDs to the 7 OUT Pins of the IC via 220Ohm Resistors. 
On my left, are the 7 digital inputs which are connected to a ribbon cable. The other end of the ribbon is submerged in the water tank with exposed terminals at various heights to detect the water levels. Along with the 7 wires, there is an eighth wire that stays at the bottom of the tank and is connected to the +ve terminal. 

As the tank starts filling up, the water level rises and a conductive path is created between the positive terminal and the base of Darlington Transistor inside the IC. Hence a logic HIGH is sent to the Input Pin of the IC which leads to the corresponding OUT Pin to go LOW lighting up the LEDs one by one starting from the bottom Red to the top Green. The bottom Red LED indicates lack of water and the top Green LED indicates that the tank is 100% full. 

You can also add a buzzer to the circuit to get an audio indication when the tank is full.
If you want to be super funky, you can also add a relay module which can turn on and off the water pump.


Breadboard Demo
---------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEingUFsmxIA1YC6NBHY2edDQ4QnMSRCN0jRmzUCVz6hFHyzG_fCyTsI4DsImtkbVwyTkhqkTgHpRici9E7SPn44s_HBdm-2_oRo2wSDsFA5lr7S2ONm-3MMvmQt4MTFPe0OyOwLSRmC05E6698ubosZTKQDwPgy6Ns87jCBmy8V7azYRR7SQYDZNYmCH9Y/w640-h360/5.png)

Before assembling the components on a PCB, lets do a quick test on a breadboard to make sure our logic works as expected.
For this demo, I am going to fill up a coffee mug with normal tap water.

As you can see, the LED indicators go up from bottom Red to the top Green as I keep filling the mug. The buzzer starts buzzing when the mug is 100% full. Hence, our setup is working as expected.


The Board
---------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj7JCcxx0AYWAtdwvGmuFLuApcuuHJ-sLWHhO_hRcak3dSErq5lXqLi2OsLU1lMiep4pBEe32DDshG26ye_-3BkRfr6uKXC3Qd1T1WQ8SSAfrBMGAdJLPzRrAd6yP40qlnDWhmupcg1ZfVPjd09v8SGLpJzXhLNQOMF_fcsjN01lV46QyQlZ3NcNayHEUQ/s1054/6.png)

So, this is how my board looks like in 2D and 3D.
If you want to learn how to design a PCB, please check out my "Tutorial No. 45: Transformers PCB BADGE", the link is in the description below.


Component Assembly
------------------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEirXgOoUYLZBCWmKJEehBcmMmDSFZ4Gx6uKuPQxN4GspEyX4hSoohnDOeP9PDgN6e_fiFZTVaZedFLrCzfx1f_DuBsmsxdQSu-SzOWG5QI-93pu3EP15H2gYj3PhHaLxQ_BIgiw-aIkGOobwcusSSD7eIOHEAkpBrSMLazkY7uFd_xFwnvflCYXWZFRRNM/s1054/7.png)

Now, lets solder the components to the board.
Lets first solder all the resistances to the board.
Then, lets solder all the LEDs to the board. I am using a 3mm Green LED as the power indicator.
Next, I am soldering the IC base to the board. Since I care a lot about my ICs and microcontrollers, I never solder them directly to the board. In case of an ICs, I always try to use an IC bases or if a base is not available I use female pin headers. 
After soldering the IC base, I am soldering the Buzzer to the board.
Now to conclude the setup, I am soldering the Ribbon Cable to the board. For my setup, I am only using half a meter long cable. But in a real-world scenario, you will definitely need a cable longer than this.

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEgjtcLGvJ8jH265iDgt-t8m-fMi7ywjKTYOhwn6Ou4DW7r4UKIsQj0TSGB1KHq-kuVaqtBdUR3ZKiNtiDlUoPHM0wl6RZmuh2n7RyPNow4HRnHIOmHyNeJOEijyd1wq9tvRgF7ZwPYSdP-RlKHjBCu3H4CIoNsOwVzrLH9aJBF-58C5sTtEB0x4UZq5kOw/w640-h360/10.png)


Final Demo
----------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEj8EUMlBKxSnam3SoDfMqUlherOXGMm2iOFP10SjfYIaVhRWlXDn2lfmE1sOgZxc9465XE-FiOBTldBGM4eCDWMHQpXbe2oZeMLl0ekdRQS89X8cELBo4-2uT0WS6-oh0ul0IGjuT9eSpN8jY6lTqzh60UAwlnRG30xfO3y0OuwzWetNR3YsAIzIQfBQzA/s1054/11.png)

So, this is how the final setup looks like.

As the water level rises, a conductive path is created between the positive terminal and the base of Darlington Transistors inside the IC. This triggers a logic HIGH at the Input Pins of the IC and the corresponding OUT Pins goes LOW lighting up the LEDs one by one starting from the bottom Red to the top Green. When the mug is 100% full the top green LED lights up and we also hear a noises of the buzzer.


Usability
---------

![image](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEjRPA3hiZCloO2pLDk1CaIFMztqgWmE8iqsSrYxfXBaF0EUUesrwO19UdlFGX1tqCOVwnMRq9lj1llnkOMVkeGsXBnnZOmuXnJy6BUzdl2KOqaYD0zXkUnwKSdlwpKEEEk7quESU74LeZOn1ruk1dbsQ5UE2TTJLhLkQO2IF-670ZGbctFYmoltOk05CQY/s1054/12.png)

To be very frank, I see more disadvantages than advantages of using this IC in building a liquid level indicator.
You may have a different opinion, but my opinion is based on the below facts:

1. The choice of the probes that will remain submerged in the liquid has to be done very carefully as they:
	- Rust, foul and deteriorate due to "corrosion" and "electrolysis" causing the LEDs to slowly fade and finally turn off.
	- Hence the probes need to be cleaned and replaced every 2 - 3 years.
2. This circuit will work well with tap water, however do not use this with salt water or with any flammable liquid. If in your house you get hardwater, there will be salt deposits on the probes and you will have to clean the salt deposits on a regular basis.
3. This circuit will not work if you have a metal tank.

Replacing the contact points with something "non-corrosive" may help but I will not put my bet on that.
Another option is to have "large electrodes" which will have a low impedance even when covered with impurities.

To conclude I would like to say that the ULN2003 is not the best device to use for this application. You might be better using a "CMOS buffer" or inverter which needs less water conductivity to operate and also gives a more sudden output change as the input voltage rises and falls, along with "non-corrosive large electrodes".


Thanks
------

[![6r3ponugs64](https://i.imgur.com/pPKiuOv.jpeg)](https://youtu.be/6r3ponugs64)

Thanks again for checking my post. I hope it helps you.
If you want to support me subscribe to my YouTube Channel: https://www.youtube.com/user/tarantula3

Video: https://youtu.be/6r3ponugs64

Full Blog Post: https://diy-projects4u.blogspot.com/2024/06/LiquidLevelIndicatorUsingULN2003.html


References
----------
DataSheet: https://github.com/tarantula3/ULN2003

All About ULN2003 IC: https://youtu.be/dtfGf7kf__g

Transformers PCB BADGE: https://youtu.be/vlJoQAzjYDo

GitHub: [View](https://github.com/tarantula3/Liquid-Level-Indicator-Using-ULN2003) 



**Support My Work:**

BTC:   1Hrr83W2zu2hmDcmYqZMhgPQ71oLj5b7v5

LTC:   LPh69qxUqaHKYuFPJVJsNQjpBHWK7hZ9TZ

DOGE:  DEU2Wz3TK95119HMNZv2kpU7PkWbGNs9K3

ETH:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

BAT:   0x9D9E77cA360b53cD89cc01dC37A5314C0113FFc3

LBC:   bZ8ANEJFsd2MNFfpoxBhtFNPboh7PmD7M2

COS:   bnb136ns6lfw4zs5hg4n85vdthaad7hq5m4gtkgf23 Memo: 572187879

BNB:   0xD64fb51C74E0206cB6702aB922C765c68B97dCD4

MATIC: 0xD64fb51C74E0206cB6702aB922C765c68B97dCD4


Thanks, ca again in my next tutorial.

