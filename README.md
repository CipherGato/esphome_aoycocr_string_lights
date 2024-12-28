# ESPHome Config for Tuya Globe Fairy/String Lights

This repo contains a sample ESPHome config for Tuya String Lights based on the BK7231T Wifi Module and [M031FC1AE](https://www.nuvoton.com/products/microcontrollers/arm-cortex-m0-mcus/m031-series/m031fc1ae/) MCU.

These lights were bought from Amazon and advertised as **Alexa Globe String Lights LED by Aoycocr**

![product](/images/product.png)

### Front of Box
![box front](/images/box_front.jpg)

### Back of Box
The back of the box shows they are made by [Shenzhen Hysiry Technology Co Ltd](http://www.hysiry.com).
![box back](/images/box_back.jpg)

###  Control Unit
The controller features 3 buttons, a microphone and can be controlled via an Infrared remote control, bluetooth (which seems to be only for enrollment) and wifi via a Tuya mobile application.
![control unit](/images/control_unit.jpg)

### PCB

Inside on one side there is a PCB with:
* the three physical buttons
* a microphone for the music synchronization effect
* a Nuvoton [M031FC1AE](https://www.nuvoton.com/products/microcontrollers/arm-cortex-m0-mcus/m031-series/m031fc1ae/) MCU used to control the LED effects and handle the microphone and IR receiver.
![circuit board front](/images/circuit_board_front.jpg)
![led controller](/images/nuvoton_M031FC1AE.jpg)

The other side of the circuit board has the familiar BK7231TQN32 which handles the Wi-Fi/Bluetooth and interfaces with the Tuya cloud.
![circuit board back](/images/circuit_board_back.jpg)

![BK7231](/images/BK7231TQN32.jpg)

## Flashing

I used [Tuya Cloudcutter](https://github.com/tuya-cloudcutter/tuya-cloudcutter) with the [57414 Vintage Cafe Lights v1.1.71 profile](https://github.com/tuya-cloudcutter/tuya-cloudcutter.github.io/blob/master/devices/enbrighten-57414-vintage-cafe-lights-v1.1.71.json) to first disable the cloud connection and then to flash the bk7231t ESP Home kickstart firmware. It was only while playing with the kickstart firmware I realised that none of the GPIO pins controlled the lights or were connected to the physical buttons. On opening the case I discovered the additional  [M031FC1AE](https://www.nuvoton.com/products/microcontrollers/arm-cortex-m0-mcus/m031-series/m031fc1ae/) MCU and therefore the configuration relies on the [Tuya MCU](https://esphome.io/components/tuya.html) component.

It took a bit of work using the IR remote control to debug what the different Datapoints were. The result of which is in the config shown below. It's a bit messy but it works:
## Configuration
https://github.com/CipherGato/esphome_aoycocr_string_lights/blob/85071d40f1fdb986971a6c71f405aabcd2e158a5/src/string-lights.yaml#L1-L457

The config includes a dashboard and should update and reflect changes made direct with the IR remote.

![Dasnboard](/images/dashboard.png)


### Resources

1. https://www.elektroda.com/rtvforum/topic3990174.html
2. https://www.elektroda.com/rtvforum/topic4011975.html