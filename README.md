# Sony Bravia Android TV for Athom Homey

Control your Sony Bravia Android TV with this Homey(Athom B.V.) app.

Before installing this app, please read these instruction very carefully:
- Enable remote start on your TV:  
   - [Settings] > [Network] > [Home Network Setup] > [Remote Start] > [On]
- Enable pre-shared key on your TV:
   - [Settings] > [Network] > [Home Network Setup] > [IP Control] > [Authentication] > [Normal and Pre-Shared Key]
- Set pre-shared key on your TV:
   - [Settings] > [Network] > [Home Network Setup] > [IP Control] > [Pre-Shared Key] > [sony]
- Give your TV a static IP address, or make a DHCP reservation for a specific IP address in your router.
- Determine the MAC address of your TV:
   - [Settings] > [Network] > [Network Setup] > [View Network Status]

#Adding your Sony Bravia Android TV to Homey

Pairing can be done in 2 ways;

1. automaticly (Homey tries to do "everything" for you, except the Pre-Shared-Key)
2. manual (you need to put the IP and Pre-Shared-Key yourself)

If you choose to pairing the device automaticly, the device will be presented unavailable with this message;

![devicesetpsk](https://cloud.githubusercontent.com/assets/601053/16109671/59724506-33aa-11e6-8176-3658de2c9a22.png)

Now you should go to the device settings and change the default '----' to the PSK of your TV.
If the 'Please set PSK' message appears, then probably the PSK is not insync with the TV. In this case please check the PSK of your TV and the PSK setting of the Homey device.


#Flows:

**Triggers (App)**:
- Connection error (timeout|refused)?

**Triggers (Device)**:
- TV turned off?
- TV turned on?
- Netflix started?
- Channel Up (+)?
- Channel Down (-)?
- Volume Up (+)?
- Volume Down (-)?
- TV muted?
- TV un mute?
- HMDI changed?
- TV options?

**Conditions**:
- TODO

**Actions**:
- Power Off
- Power On
- Netflix
- Channel Up (+)
- Channel Down (-)
- Volume Up (+)
- Volume Down (-)
- Mute
- Un Mute
- Set Input (HDMI 1/2/3/4)
- Options

#Speech support
- not (yet)

#API support
- not (yet)

#Translation
- english
- dutch (todo)

#Credits
A great app, originally created by Marco Frijmann. As Marco stopped support, I took the app under my wings (with permission of MarcoF).

**Use at your own risk, I accept no responsibility for any damages caused by using this script.**

#known issues
- connection timeout|refuse;

|  timeout   |  refused   |
| --- | --- |
| ![deviceconnectiontimeout](https://cloud.githubusercontent.com/assets/601053/16109481/5787901c-33a9-11e6-823e-9136a3cb5fc8.png)   | ![deviceconnectionrefused](https://cloud.githubusercontent.com/assets/601053/16109482/57879d3c-33a9-11e6-870f-7e3b726470d2.png)   |
  As of a unknown reason Homey loses connection with the TV. In the case this happens the device will become unavailable.
  To trackdown this issue, you could make flows like these;
![flowconnectionrefused](https://cloud.githubusercontent.com/assets/601053/16109290/49dce1c0-33a8-11e6-870d-9814e6688eef.png)
![flowconnectiontimeout](https://cloud.githubusercontent.com/assets/601053/16109371/c8ea27e8-33a8-11e6-8d1c-b5a2229092cf.png)

#Compatibility
Homey version >= 0.8.38 (due to wrench/settings fix)

#Buy me a beer/pizza/holiday?
[![](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=KWMTEXY3U6VVN&lc=GB&item_name=HomeyApp&item_number=SonyBraviaApp&currency_code=EUR&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHosted)


# Changelog
**Version 0.4.3:**
- Bugfix

**Version 0.3.2:**
- first implementation of WOL for older TV's

**Version 0.3.1:**
- Try to fix connection refused/timeout
- First attempt to support older(between 2013-2015) bravia models

**Version 0.3.0:**
- First public release
