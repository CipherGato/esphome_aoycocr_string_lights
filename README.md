# ESP HOME Config for Tuya String Lights

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


https://github.com/CipherGato/esphome_aoycocr_string_lights/blob/85071d40f1fdb986971a6c71f405aabcd2e158a5/src/string-lights.yaml#L1-L457


Resources

1. https://www.elektroda.com/rtvforum/topic3990174.html
