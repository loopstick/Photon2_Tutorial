## Particle Publish/Subscribe demo by TJ McLeish

The following code is a very basic publish + subscribe demonstration using 2 photons claimed on the same account.  One device publishes a 'toggle-led' event, and the other subscribes to 'toggle-led' events.  When device A publishes an event, device B turns on its internal LED [the blue one by the usb connector] for 500 milliseconds.


// Flash the following code onto a Photon2 (Device A).
```
// Device A
void setup() {
    // Set pin D7 as an OUTPUT pin to control an LED
    pinMode(D7, OUTPUT);
}
void loop() {
    // Publish the "toggle-led" event with the device ID as data
    // This sends a message to other devices or services
    // String(System.deviceID()) gets the device ID and converts it to a string
    Particle.publish("toggle-led", String(System.deviceID()));
    // Turn on the LED connected to pin D7
    digitalWrite(D7, HIGH);
    // Wait for 250 milliseconds (0.25 seconds)
    delay(250);
    // Turn off the LED
    digitalWrite(D7, LOW);
    // Wait for 4750 milliseconds (4.75 seconds)
    delay(4750);
}
```

Flash the following code onto a different Photon2 claimed to the same account (Device B).
```
// Device B
void setup() {
    // Set pin D7 as an OUTPUT pin to control an LED
    pinMode(D7, OUTPUT);
    // Subscribe to the "toggle-led" event
    // This allows the device to listen for a specific event
    // and call the 'toggleLed' function when that event is received
    Particle.subscribe("toggle-led", toggleLed);
}
void loop() {
    // Device B's loop can remain empty as it only listens for events
    // This loop continuously runs, but there's no specific code in it
}
void toggleLed(const char *event, const char *data) {
    // Toggle the LED on Device B
    // Turn on the LED
    digitalWrite(D7, HIGH);
    // Wait for 500 milliseconds (0.5 seconds)
    delay(500);
    // Turn off the LED
    digitalWrite(D7, LOW);
    // The LED is turned on and off in response to the event
}
```

***
### Another demonstration of 2 particle devices communicating with each other via publish and subscribe.  

It works with devices claimed to the same account.  The demo includes using the OLED, a custom splash screen, a button, a debug serial logger, and OpenProcessing.  

Here is the link to the code via the WebIDE:  https://go.particle.io/shared_apps/652ca6e501c674011e9a0e36  

Comments and links are embedded in the code.
