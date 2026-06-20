# OpenWatch Project
Project OpenWatch is the initiative undertaken by BLOCKS, who came into the limelight for their modular smartwatch. The goal of this initiative is to make a fully open source OS so any smartwatch that can have AOSP builds or be ported to AOSP can have a fully functional Watch OS.

If you are building **LineageOS 14.1** on Ubuntu 18.04 LTS, run the following command: `export LC_ALL=C`

Here is a link to see our current to-do, in progress, done list https://goo.gl/62UnLw

IMPORTANT: The OpenWatch Project only supports MediaTek based watches (for now). Newer Unisoc devices *might* be supported in the future, once most development for MediaTek devices is finished.

# Build for Harmony

List of confirmed working devices under the harmony name (Probably more out there):
* Kingwear KW88, KW98, KW99
* Blocks Watch
* Look Watch
* Zeblaze Thor, Thor S
* Lemfo LES1
* IQ I2
* Diggro DI01, DI07

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/harmony/twrp.md)

[Build Android 8.1](https://github.com/OpenWatchProject/readme/blob/master/harmony/android-8.1.md)

# Build for InHarmony

List of confirmed working devices under the inharmony name (Probably more out there):
* Diggro DI06

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/inharmony/twrp.md)

# Build for AntiHarmony

List of confirmed working devices under the antiharmony name (Probably more out there):
* HEHUI variants of harmony
* Microwear H2

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/antiharmony/twrp.md)

# Build for Infinity

List of confirmed working devices under the infinity name (Probably more out there):
* Lemfo LEM7
* Zeblaze Thor 4
* IQI I7
* IQI I8

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/infinity/twrp.md)

[Build Android 7.1](https://github.com/OpenWatchProject/readme/blob/master/infinity/android-7.1.md)

# Build for Edge

List of confirmed working devices under the edge name (Probably more out there):
* LEMFO LEMX

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/edge/twrp.md)

# Build for Unity

List of confirmed working devices under the unity name (Probably more out there):
* Kingwear KW06

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/unity/twrp.md)

# Build for Continuum

List of confirmed working devices under the continuum name (Probably more out there):
* Lemfo Lem5 Pro
* Finow X5 Air

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/continuum/twrp.md)

# Build for Expanse

List of confirmed working devices under the expanse name (Probably more out there):
* Zeblaze Thor Pro

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/expanse/twrp.md)

# Build for Wisp

List of confirmed working devices under the wisp name (Probably more out there):
* X02S MT6580
* X01S Plus MT6580

[Build TWRP Recovery](https://github.com/OpenWatchProject/readme/blob/master/wisp/twrp.md)

# For Zeblaze Smart Watch

Someone has managed to activate developer options on Zeblaze Thor Ultra.
Open Phone app and type *#*#83781#*#*
On the second tab, activate USB debugging.


I then used the program "ADB App Control" for windows:

https://adbappcontrol.com/en/

The program manages everything (drivers etc.), so using ADB is plug and play.

Connect the watch to the pc with the charging cable , which is usable for data transfer too (two of the for pins are for data transport).

You can now manage apps etc. comfortably from your pc and don't have to fiddle around with the small watch screen.

But even better: You can change all system options even developer options with adb commands in the console of ADB App Control!

F.ex.: I wanted to use an external bluetooth gps with the watch, because the built-in gps of the watch is crap.

To do this you have to allow mock locations and a special mocking app (I use the app "bluetooth GNSS" as mocking app with a garmin glo 2 bluetooth gps-receiver).

These options are developer options, so you cannot acces them via the system settings on the watch because developer options

It looks like that in the console:

Type:

adb shell settings put secure mock_location 1 

(Use 1 to enable and 0 to disable)

then type:

adb shell appops set com.example.my.package android:mock_location allow

In my case the adb-package-name of the app "bluetooth gnss" is "com.clearevo.bluetooth-gnss" so you have to replace "com.example.my.package" with that.

In my case everything worked fine!
With ADB you can change all developer options.
All you have to do is to find the right commands for the console using google.
