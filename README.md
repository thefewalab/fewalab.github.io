# Fewalab Industries

### ESP12 Pinouts

<img src="images/esp12-fancy-pinout-.png" width=500>

## v1.0.0

### Programming the board.

<img src="images/programming.jpg" width=500>

Reference: https://circuitjournal.com/esp8266-with-arduino-ide

This method does not use any switch presses but instead uses RTS pin of the FTDI module.

<img src="images/esp-programming.jpg" width=500>

### Sample Programs

<img src="images/arduino-setup.png" width=500>

The above setup is needed in arduino IDE to program the board.
1. Buzzer

```
void setup() {
    pinMode(13, OUTPUT);
}
void loop() {
  digitalWrite(13, HIGH);   
  delay(1000);                       
  digitalWrite(13, LOW);    
  delay(1000);                       
}
```
2. Relay
```
void setup() {
 pinMode(4, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(4, HIGH);   
  delay(1000);                       
  digitalWrite(4, LOW);   
  delay(1000);                       
}
```


### Plus Points
However there is a plus point in this design.
- When a 5V power supply is used it cal also trigger a 6V Relay.

### Error in v1.0.0

There as some errors in this design:
- The Vpower was not connected to 5V in the schematic
- The switch was connected to ADC of the ESP12 Chip, but in chip the max voltage is 1V, so a voltage divider is needed in case we need to supply 1V instead of 3.3V
- While programming RST pin of the ESP is connected to RTS of FTDI so, some changes in the programming header is required to make it easier to program via FT232 module.
