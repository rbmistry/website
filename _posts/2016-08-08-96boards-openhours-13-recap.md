---
author: jennifer.castelino
comments: true
date: 2016-08-08 15:28:16+00:00
layout: post
link: https://www.96boards.org/blog/96boards-openhours-13-recap/
slug: 96boards-openhours-13-recap
image: /assets/images/blog/OpenHours-03.png
image_name: OpenHours-03.png
title: 96Boards OpenHours 13 Recap
wordpress_id: 16170
Boards:
- DragonBoard 410c
- HiKey
category: blog
tags:
- 64-bit
- 96Boards
- aarch64
- Android
- ARM
- ARMv8
- Breakout
- Bubblegum
- bubblegum-96
- CE
- Consumer Edition
- Consumer IoT
- DB410c
- Docker
- dragonboard410c
- HiKey
- Library
- Linux
- Low speed expansion header
- Open Embedded
- Open Hours
- OpenHours
- Reference Platform
- rpb
- sensors
- UART
---

96Boards OpenHours continued this week with our between season format of holding a casual open hour to allow attendees to ask questions of Linaro's developers.  We started these open session Q&A with our session 10 and continued it this week with session 13.  This was an hour to have people hangout and ask whatever questions people may have about 96Boards.  To watch this weeks’ session go to (https://youtu.be/gqN2YdRUuPw)

{% include media.html media_url="https://www.youtube.com/embed/gqN2YdRUuPw?feature=oembed" %}

Last week in the hangout Robert shared a link to allow people to submit topics or questions for the developers on the hangout.  The link is:[ https://discuss.96boards.org/t/openhours-topic-suggestion/ ](https://discuss.96boards.org/t/openhours-topic-suggestion/)and Robert will take these suggestions and try to incorporate these into future OpenHours.  This week began with a question about _Bluetooth_ ® wireless technology and board support.  This was regarding Bluetooth Low Energy spec and this is a new generation of Bluetooth.  Robert mentioned bringing in one of the Linaro developers to help with this in more detail.  The team also worked with a community member that was having trouble with their board bring up.  The next topic was a battery question regarding the Dragon board and charging a battery off the board.  There was then a discussion about the software needed to do this, Robert offered to bring in the Linaro expert to help with this.  The community member will bring in the board to the call and get it hooked up with Linaro's help.  The next question was do you need an external signal for the GPS?  Akira explained that the weak signal is due to the certification and the Dragon board has a weak antenna as well.  There was a lot of discussion around this issue and possible solutions.  Mark then discussed some of the new devices he has seen and been using.  The discussion then turned to ideas of all kinds of different items that could be built.  The next question was about the pin outs on the HiKey Android boards, since there are many different boards no one knew that readily. At the end of the call Robert announce a Dragon Board give-away in the future in August.   There will be more information coming soon about the give-away.  As always there is a lot of good information and resources that was given in the chat below, this is a great place to get more detailed information.

Don't forget about the upcoming Linaro Connect where attendees have an opportunity to meet with Linaro in person and learn a lot more about what is going on in the community.  There are still openings available to attend this conference in Las Vegas, Nevada September 26-30, 2016 --[http://connect.linaro.org/](http://connect.linaro.org/).

Be sure to join us for the next OpenHours  [https://www.96boards.org/openhours/](/openhours/).  Next week during session 13 we will have another open hour to just answer questions.  So join us and bring all your 96Board questions and we will try to answer them all for you.

Please remember, if you get stuck, there are resources to help you through the installation. Feel free to check out the [96Boards forums](https://discuss.96boards.org/), [96Boards wiki](https://github.com/96boards/documentation/wiki), or [Freenode IRC](http://webchat.freenode.net/?channels=%2396boards) channel #96boards (there are many ways to access IRC, this website is one of them). Dig around the wiki, create a new forum thread, and/or post a question in the chat.

**Below is the chat log from the OpenHours session today:**

```
Guest 8
G8
Bluetooth Low Energy
MB
BLE is a new Bluetooth spec
AT
[http://stackoverflow.com/questions/17835469/using-bluetooth-low-energy-in-linux-command-line](http://stackoverflow.com/questions/17835469/using-bluetooth-low-energy-in-linux-command-line)
MB
Tne new spec works a lot like Zigby
YZ
Dragonboard 410c supports piconet setup, which gives you master/client as well as 1-1 pairing
sorry i cannt open video or micro
DM
sudo hciconfig hci0 lestates`
MB
I don't know for sure, but I believe BLE would need hardware changes in the base design unless that was taken into account from the outset.
RW
[http://builds.96boards.org/releases/dragonboard410c/linaro/rescue/latest/](http://builds.96boards.org/releases/dragonboard410c/linaro/rescue/latest/)
AT
[http://seeedstudio.com/depot/96Boards-UART-p-2525.html?cPath=122_163](http://seeedstudio.com/depot/96Boards-UART-p-2525.html?cPath=122_163)
YZ
we can check the schematics to see whether PMIC charging is present
DM
[http://linaro.co/db410c-schematics](http://linaro.co/db410c-schematics)
Above for Hardware Manual
Check 8 Power management
AT
[https://discuss.96boards.org/t/acquiring-a-power-adapter-for-the-dragonboard-410c/](https://discuss.96boards.org/t/acquiring-a-power-adapter-for-the-dragonboard-410c/)
MB
Great idea... an adapter pack for power plug.
MW
there appears to be hardware support for charging via VBUS on the USB device connector
MB
I bought a 50 pack of the power adapter plug on Ebay, can see part# in picture [http://www.ebay.com/itm/351596615215?_trksid=p2057872.m2749.l2649&ssPageName=STRK:MEBIDX:IT](http://www.ebay.com/itm/351596615215?_trksid=p2057872.m2749.l2649&ssPageName=STRK:MEBIDX:IT)
YZ
so quick look the pmic8916 is simulating battery supply via 3.7 BUCK output to PMIC VBAT+BAT_SNS
AT
[https://discuss.96boards.org/t/gps-and-wifi-antenna/](https://discuss.96boards.org/t/gps-and-wifi-antenna/)
RW
sudo hciconfig hci0 lestates`
DM
Ok THanks Marc for letting me know..
MB
Jean-Marc, that is GREAT news
DM
If you could just let me know the output of the above command will be gr8..
RW
[https://apkpure.com/](https://apkpure.com/)
J
apkpure
DM
Bluetooth Low Energy 4.0Type of devices- Central: can receive broadcast messages and can connect with peripheral devices too.- Observer : only listens to broadcast messages- Peripheral : Sends Broadcast Messages at regular interval and can be connected for more content / interaction- Broadcaster: sends broadcast messages at regular intervals ( can not connect)
J
This is not the standard plug for Dragonboard hahaha
YZ
UCRobotics already have a design powering over battery
R
[https://github.com/96boards/documentation/blob/61c99db9efb8dca9f80c415c5e1cb5334c5f29ce/ConsumerEdition/CE-Extras/GPIO/PinOuts/HiKey_Debian_pinout.jpg](https://github.com/96boards/documentation/blob/61c99db9efb8dca9f80c415c5e1cb5334c5f29ce/ConsumerEdition/CE-Extras/GPIO/PinOuts/HiKey_Debian_pinout.jpg){:class="img-responsive lazyload"}
YZ
nope, I wouldn't remember
there are just too many boards in my head right now
MB
this is Levi's web source address, he would love to print & ship [https://www.3dhubs.com/anchorage/hubs/lostinthe907](https://www.3dhubs.com/anchorage/hubs/lostinthe907)  He is also part of a much larger network of people that will do just this and some have design capablility
AT
#define GPIO_A 23#define GPIO_B 24#define GPIO_C 25#define GPIO_D 26#define GPIO_E 27#define GPIO_F 28#define GPIO_G 29#define GPIO_H 30#define GPIO_I 31#define GPIO_J 32#define GPIO_K 33#define GPIO_L 34
RW
#96Boards
AT
A is 488 for HiKey -  have not tried with Android
RW
sdrobertw
DM
What kind of LCD ?
AT
[http://www.seeedstudio.com/wiki/Grove_-_LCD_RGB_Backlight](http://www.seeedstudio.com/wiki/Grove_-_LCD_RGB_Backlight)
RW
[https://www.96boards.org/product/sensors-mezzanine/](/product/sensors-mezzanine/)
[https://www.arrow.com/en/products/102990344/seeed-technology-limited](https://www.arrow.com/en/products/102990344/seeed-technology-limited)
MW
[https://www.seeedstudio.com/96Boards-Sensors-p-2617.html](https://www.seeedstudio.com/96Boards-Sensors-p-2617.html)
RW
[96boards.org/blog](https://96boards.org/blog)
MW
you can buy the sensor board alone from seeed for less than arrow
```

{% include image.html path="/assets/images/blog/OpenHours.png" alt="OpenHours Image" class="img-fluid" %}



Click here to join us for [next OpenHours ](/openhours/)
