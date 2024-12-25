# LED-Multiplexing
This project uses MAX7219 dot matrix to display characters using Arduino UNO microcontroller.

# AIM:
Using MAX7219 library to generate different rolling LED patterns such as numbers, alphabets, scrolling text, symbols, emojis, etc. Apart from this, we can also display some sensor data like DHT11/DHT22 on this display for temperature and humidity.

# Components required:
1.	Arduino UNO Board
2.	8x32 Led Matrix using MAX7219 display
3.	Jumper wires
4.	Power supply
5.	DHT11 sensor

# Procedure:
1.	Input connectors:
  1.	Connect the vcc(for external power supply) to the chip pin.
  2.	Connect ground pin(GND) to arduino.
  3.	Connect The Data pin(DIN).
  4.	Connect Load(CS/Load) to any pin of the microcontroller.
  5.	Connect clock pin(CLK) to any pin on the microcontroller.
2.	Output connectors:
  1.	VCC connects to 5V on the next module.
  2.	GCC connects to GND on the next module.
  3.	DOUT is Data Out and connects to the DIN pin of the next module.
  4.	CS/LOAD  connects to CS / LOAD on the next module.
  5.	CLK  connects to CLK on the next module.
3.	Downloading Arduino software/ using web version
4.	Library Installation: MD_MAX72XX by MajicDesigns
