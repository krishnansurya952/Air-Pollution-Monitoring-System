Title: Air Quality Monitoring System with LCD Display

Abstract:
This project implements an air quality monitoring system using Arduino and various analog sensors. The system measures the concentration of certain gases using MQ135 and MQ4 gas sensors and also monitors the humidity level using a dedicated sensor. The obtained data is displayed on a 16x2 character LCD screen and is also logged in the Serial Monitor for debugging purposes.

1. Introduction:
Air pollution and indoor air quality have become crucial concerns for health and environmental reasons. This project aims to provide a simple and cost-effective solution for monitoring air quality and humidity in a confined space using Arduino and gas sensors. The LCD display provides real-time readings, allowing users to monitor the air quality in their surroundings.

2. Hardware Components:

Arduino board (e.g., Arduino UNO)
MQ135 gas sensor
MQ4 gas sensor
Humidity sensor (e.g., DHT11 or DHT22)
16x2 character LCD with I2C interface
Breadboard and jumper wires for connections
3. Libraries Used:
The project utilizes the "LiquidCrystal_I2C" library for communicating with the I2C-based LCD display.

4. Implementation:
The code is divided into the setup and loop functions. The setup function initializes the LCD and Serial communication, while the loop function performs the main operations.

4.1. Setup Function:

Initializes the LCD display using the "LiquidCrystal_I2C" library, clears the display, and turns on the backlight.
Begins the Serial communication at a baud rate of 9600 for debugging purposes.
Prints the initial message "Air Quality:" on the first row of the LCD.
4.2. Loop Function:

Reads analog values from the MQ135, MQ4, and humidity sensors connected to specific Arduino pins (A0, A1, A2, and A3).
Converts the analog values to corresponding voltages using the 5V reference and 10-bit ADC resolution.
Calculates the PPM (parts per million) values for MQ135 and MQ4 gases based on specific sensor formulas.
Displays the MQ135 PPM value on the second row of the LCD and prints it to the Serial Monitor.
Delays for 1 second to allow time for the value to be read and displayed.
Clears the second row of the LCD.
Displays the MQ4 PPM value on the second row of the LCD and prints it to the Serial Monitor.
Delays for 1 second to allow time for the value to be read and displayed.
Clears the second row of the LCD.
Displays the humidity voltage value on the second row of the LCD and prints it to the Serial Monitor.
Delays for 2 seconds before the loop repeats.
5. Sensor Data Conversion:

The analog readings from the sensors are converted to corresponding voltages using the formula: Voltage = (AnalogValue * 5.0) / 1023.0.
6. Gas Sensor PPM Calculation:

MQ135 PPM is calculated using the formula: PPM = (9.9 * pow((Voltage / 5.0), -1.5)) - 0.1.
MQ4 PPM is calculated using the formula: PPM = pow(10, ((log10(Voltage / 5.0) - 1.2535) / (-0.2375))).
7. Results and Display:
The LCD displays real-time PPM values for MQ135 and MQ4 gases, as well as the humidity voltage. The Serial Monitor also logs the same data, allowing for further analysis and debugging if required.

8. Conclusion:
The air quality monitoring system using Arduino and gas sensors provides a simple and inexpensive way to monitor indoor air quality and humidity. The project demonstrates the capability of Arduino to interface with sensors and display data on an LCD screen. Users can further enhance the system by adding more sensors or incorporating data logging and cloud connectivity for remote monitoring and analysis. Proper calibration and accuracy verification of the gas sensors are essential to ensure reliable air quality measurements.
