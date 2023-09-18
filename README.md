## Hands-on Photon2 Tutorial

**This tutorial created by Sudhu Tewari 2023**
 - from materials originally created by: Michael Shiloh and Judy Castro for *Teach Me To Make*

#### Tutorial overview
The tutorial will focus on getting you up and running with Particle Photon2 quickly, so that you will understand the basic procedures for working with your [Particle Photon2](https://docs.particle.io/photon-2/)

We will cover how to connect your Photon2 to your laptop; how to understand, modify, and write programs (aka code); how to connect input devices and sensors to your Photon2 and read them from a program; and how to connect actuators (LEDs, motors, speakers) and control them from a program. Other topics will be covered as interest dictates and time permits.

#### What is the Photon2 anyway?
 - Read about the Photon2: https://docs.particle.io/reference/datasheets/wi-fi/photon-2-datasheet/#functional-description

 - Photon2 GPIO pins and ports: https://docs.particle.io/reference/datasheets/wi-fi/photon-2-datasheet/#pin-markings
 ![photon-2-pinout](/images/photon-2-pinout.svg)

- Getting Started Dashboard: https://docs.particle.io/getting-started/getting-started/

### Start Here

- ~Install IDE~

#### Initial Set Up (first time only)
- Follow the steps at [setup.particle.io](https://setup.particle.io/)
  to get your Photon2 set up

#### Configure Wi-Fi (first time at home)
- in order to do anything with your Photon2 must be connected to wifi
  - This isn't totally true, you _can_ work with the Photon2 not connected to Wi-Fi _BUT_ it's a bit complicated and we're aiming for simple and easy in this tutorial.
  - luckily Particle has made it easy to configure wifi for Photon2
- Navigate to: https://docs.particle.io/tools/developer-tools/configure-wi-fi/
  - follow the prompts to enter your wifi credentials
     - Wi-Fi Network name
     - password

#### Configure Photon 2 to connect with Cal IoT Wi-Fi (required to use your Photon2 on campus)
- In order to use Cal Wi-Fi with our Photons we must register our device with the Berkeley IoT Wi-Fi network
- In order to register the device we must first obtain the MAC address of our device
- The code below asks the device to print its own MAC address (to serial):
- First we need to flash the code to our device.
- go here -> [GetMacAddress.ino](https://go.particle.io/shared_apps/6507d59801c67400099a4ce3) (right-click: Open Link in New Tab)

![WebIDE_01](/images/WebIDE_01.png)
<!--  We 'll use the Particle Web IDE [https://build.particle.io/](https://build.particle.io/build/new) to flash this code  our device. 
-->
- You should see your device name in the lower right of the Web IDE window

![WebIDE_01_Device](/images/WebIDE_01_Device.png)

- Click on the lightning bolt icon to flash the code to your device

![WebIDE_01_Flash](/images/WebIDE_01_Flash.png)
- you should see some evidence of activity.
  - you'll see a spinning arrow animation where the lightnining bolt was
  - the RGB LED on your Photon 2 will blink various colors
  - text at the bottom of the screen will let you know if the flash is successful
- When the activity stops you should see the word ```Ready.``` at the bottom of the screen
- It's working!!
  - but why can't we see anything happening?
- Use the [Particle USB serial debug log](https://docs.particle.io/tools/developer-tools/usb-serial/) to monitor the serial output. (right-click: Open Link in New Tab)
- BAM! There's your device's MAC address.
  
<!-- ![USBserialLog_MACaddress2](/images/USBserialLog_MACaddress2.png)--> 
- Copy this address!!


### Alternate methods of connecting to Wi-Fi exist! 
- Install VSCode: [TDF-Software: Installing](https://github.com/Berkeley-MDes/desinv-202/wiki/TDF-Software:-Installing)
- Connect to Berkeley IoT Wi-Fi: [Particle: connecting a Photon 2 to the UCB IoT network](https://github.com/Berkeley-MDes/desinv-202/wiki/Particle:-connecting-a-Photon-2-to-the-UCB-IoT-network)
 
### Connected to Berkeley IoT Wi-Fi? Let's continue!

- To keep things simple we'll begin writing code (apps) in the [Particle Web IDE](https://build.particle.io/build/new)


