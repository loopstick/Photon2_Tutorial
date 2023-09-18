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
- copy the code below

```
void setup() {
  Serial.begin();
}

void loop() {
  byte mac[6];
  WiFi.macAddress(mac);
  for (int i=0; i<6; i++) 
    Serial.printf("%02x%s", mac[i], i != 5 ? ":" : "\r\n");
  delay(1000);
}
```
- go here -> [https://build.particle.io/](https://build.particle.io/build/new)
- 
- We can monitor our device's serial output here: https://docs.particle.io/tools/developer-tools/usb-serial/

- 

### Alternate methods of connecting to Wi-Fi exist! 
- Install VSCode: [TDF-Software: Installing](https://github.com/Berkeley-MDes/desinv-202/wiki/TDF-Software:-Installing)
- Connect to Berkeley IoT Wi-Fi: [Particle: connecting a Photon 2 to the UCB IoT network](https://github.com/Berkeley-MDes/desinv-202/wiki/Particle:-connecting-a-Photon-2-to-the-UCB-IoT-network)
 
### Connected to Berkeley IoT Wi-Fi? Let's continue!

- To keep things simple we'll begin writing code (apps) in the [Particle Web IDE](https://build.particle.io/build/new)


