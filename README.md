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
## 1. Input connectors:
     --> Connect the vcc(for external power supply) to the chip pin.
     --> Connect ground pin(GND) to arduino.
     --> Connect The Data pin(DIN).
     --> Connect Load(CS/Load) to any pin of the microcontroller.
     --> Connect clock pin(CLK) to any pin on the microcontroller.
## 2. Output connectors:
     --> VCC connects to 5V on the next module.
     --> GCC connects to GND on the next module.
     --> DOUT is Data Out and connects to the DIN pin of the next module.
     --> CS/LOAD  connects to CS / LOAD on the next module.
     --> CLK  connects to CLK on the next module.
## 3. Downloading Arduino software/ using web version
## 4. Library Installation: MD_MAX72XX by MajicDesigns

# Circuit Diagram:
     
<img width="311" alt="Screenshot 2024-12-25 114533" src="https://github.com/user-attachments/assets/1e1c77e2-8080-4386-8566-b416f6117546" />
<img width="313" alt="Screenshot 2024-12-25 114550" src="https://github.com/user-attachments/assets/0f7b1c64-072e-4754-a640-1b380813988b" />
<img width="185" alt="Screenshot 2024-12-25 114605" src="https://github.com/user-attachments/assets/83a5f1e5-4f16-40a5-a7a4-6199c13e08b6" />
<img width="197" alt="Screenshot 2024-12-25 114620" src="https://github.com/user-attachments/assets/80adbd47-4596-41a7-8f3b-ee1eeff47d47" />


# Code:
     #include <MD_Parola.h>
     #include <MD_MAX72xx.h>
     #include <SPI.h>
     
     // Uncomment according to your hardware type
     #define HARDWARE_TYPE MD_MAX72XX::FC16_HW
     //#define HARDWARE_TYPE MD_MAX72XX::GENERIC_HW
     
     // Defining size, and output pins
     #define MAX_DEVICES 4
     #define CS_PIN 3
     
     // Create a new instance of the MD_Parola class with hardware SPI connection
     MD_Parola myDisplay = MD_Parola(HARDWARE_TYPE, CS_PIN, MAX_DEVICES);
     
     void setup() {
     	// Intialize the object
     	myDisplay.begin();
     
     	// Set the intensity (brightness) of the display (0-15)
     	myDisplay.setIntensity(0);
     
     	// Clear the display
     	myDisplay.displayClear();
     
     	myDisplay.displayScroll("Hello", PA_CENTER, PA_SCROLL_LEFT, 100);
     }
     
     void loop() {
     	if (myDisplay.displayAnimate()) {
     		myDisplay.displayReset();
     	}
     }
