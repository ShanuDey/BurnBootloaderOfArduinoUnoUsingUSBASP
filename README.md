# BurnBootloaderOfArduinoUnoUsingUSBASP


Introduction : Arduino Bootloader.


If you are building your own Arduino, or need to replace the microcontroller of your arduino board you have to burn bootloader before using your chip with Arduino IDE.
Atmel AVRs are great little ICs, but they can be a bit tricky to program. You need a special programmer and some fancy .hex files, and its not very beginner friendly. The Arduino has largely done away with these issues. They’ve put a .hex file on their AVR chips that allows you to program the board over the serial port, meaning all you need to program your Arduino is a USB cable.
The bootloader is basically a .hex file that runs when you turn on the board. It is very similar to the BIOS that runs on your PC. It does two things. First, it looks around to see if the computer is trying to program it. If it is, it grabs the program from the computer and uploads it into the ICs memory (in a specific location so as not to overwrite the bootloader). That is why when you try to upload code, the Arduino IDE resets the chip. This basically turns the IC off and back on again so the bootloader can start running again. If the computer isn’t trying to upload code, it tells the chip to run the code that’s already stored in memory. Once it locates and runs your program, the Arduino continuously loops through the program and does so as long as the board has power.

 

Requirement:

1. USBASP Programmer.

2. Any Arduino board.

3. Arduino IDE installed in your PC.

 
******************************************************************************
Hardware Setup:

Connect arduino uno isp pins with usbasp
take help of the arduino uno isp pinout
VCC --> VCC
GND --> GND
SS --> RESET
SCK --> SCK
MOSI --> MOSI
MISO --> MISO

Note: keep the Jumper (J1) always connected. [for the USBASP which have jumper J1]

************************************************************************************
Uploading Bootloader:

Fix your new microcontroller (Atmega 328 for Arduino UNO) in your Arduino Board. Open ArduinoIDE.
open tools menu in ardruino ide and 
1) Select your Board:Arduino UNO in this case.You can upload Bootloader in all type of Arduino board using USBASP programmer.
2) Select Programmer: USBasp
3) Click on Burn Bootloader
**********************************
Your new Arduino is ready to use.
**********************************
