# MusicBox
##Description
This box is an elegant way to control your music. The Music Box is controlled by only a rotary encoder so there is no unnecessary information. The controls are straight forward and elegant.

##How does it work?
In the box there is a MP3 decoder board and Arduino UNO. The Arduino controls the decoder board via a npn transistor that emulates a button press on the decoder board. So instead of four push buttons now there is one input device, the rotary encoder.

##Wiring:

                                          +-----+
             +----[PWR]-------------------| USB |--+
             |                            +-----+  |
             |         GND/RST2  [ ][ ]            |
             |       MOSI2/SCK2  [ ][ ]  A5/SCL[ ] |   
             |          5V/MISO2 [ ][ ]  A4/SDA[ ] |    
             |                             AREF[ ] |
             |                              GND[ ] |
             | [ ]N/C                    SCK/13[ ] |   
             | [ ]IOREF                 MISO/12[ ] |   
             | [ ]RST                   MOSI/11[ ]~|   Next / v++
             | [ ]3V3    +---+               10[ ]~|   Repeat
             | [ ]5v    -| A |-               9[ ]~|   Play / Pause
             | [ ]GND   -| R |-               8[ ] |   Prev / v--
             | [ ]GND   -| D |-                    |
             | [ ]Vin   -| U |-               7[ ] |   
             |          -| I |-               6[ ]~|   
             | [ ]A0    -| N |-               5[ ]~|   
             | [ ]A1    -| O |-               4[ ] |   
    DT       | [ ]A2     +---+           INT1/3[ ]~|   
    CLK      | [ ]A3                     INT0/2[ ] |   SW 
             | [ ]A4/SDA  RST SCK MISO     TX>1[ ] |   
             | [ ]A5/SCL  [ ] [ ] [ ]      RX<0[ ] |   
             |            [ ] [ ] [ ]              |
             |  UNO_R3    GND MOSI 5V  ____________/
              \_______________________/

##Part list:
* Arduino Uno
* Rotary encoder module
* Knob
* Speaker
* MP3 decoder board

##Encoder functions
Motion | Function
-------|---------
Turn left slow | Previous
Turn left fast | Volume down
Turn right slow | Next
Turn right fast | Volume up
Click | Play / Pause

##Required libraries
* [ClickEncoder](https://github.com/0xPIT/encoder)
