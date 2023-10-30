# Start Sensor System

## Function of the Subsystem

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/Start%20Block%20Diagram.png)
Figure 1: Start Sensor Block Diagram

The Start Sensor System plays a pivotal role in launching the robot's predefined course. It employs an RGB color sensor programmed to identify a green LED, which marks the beginning of the robot's journey. Upon powering the sensor, if it detects the specified green color, it promptly communicates this information to the Main Controller. 

To ensure operational robustness and mitigate the risk of sensor malfunction, a fail-safe option is in place. This involves a manual button that can be pressed in the event of sensor failure or unexpected issues. This redundancy enhances the robot's reliability and resilience in practical applications.


## Constraints and Standards

| Number | Constraint Description | Origin |
|--------|------------------------|--------|
| 1. | The RGB Sensor shall detect a spectrum of green light from an LED | Competition Specifications |
| 2. | The RGB Sensor will treat any voltage at or above 4.0V as a HIGH signal and anything below 4.0V as a LOW signal. | Sensor Specifications |
| 3. | The RGB Sensor shall detect the light within 3 seconds of light being turned on | Strategy Specifications |
| 4. | The RGB Sensor shall be placed between 3.7 to 4.3 inches from the ground | Competition and Sensor Specifications |
| 5. | The RGB Sensor shall be located with in a length range of 0.5 inches of the Green Light LED location | Competition and Sensor Specifications |
| 6. | The RGB Sensor shall be located in a width range around around 3 inches from the wall to the middle of of the Green Light LED location | Competition and Sensor Specifications |

## Buildable Schematic

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/Wiring%20Diagram.png)
Figure 2. Wiring Diagram for Start Sensor

The APDS-9960 is a digital RGB, ambient light, proximity, and gesture sensor that operates through I2C communication. 

VL (Optional Power): Pin 1 can be used to provide optional power to the IR LED used for proximity and gesture sensing. If the PS jumper is not connected, you can supply power to the IR LED through this pin. The voltage can range from 3.0V to 4.5V. 

GND (Ground): Pin 2 connects to the ground of the circuit, providing a common reference point for electrical signals. VCC (Power Supply): Pin 3 is used to power the APDS-9960 sensor board. It requires a voltage supply between 2.4V and 3.6V. 

SDA (Serial Data Address): Pin 4 is part of the I2C communication interface. It's used to transfer data to and from the sensor when connected to a microcontroller. It is typically connected to the SDA pin on your microcontroller or I2C bus. 

SCL (Serial Clock Line): Pin 5 is the clock line for I2C communication. It provides the clock pulses necessary for synchronized data transfer. It's usually connected to the SCL pin on your microcontroller or I2C bus. 

INT (External Interrupt): Pin 6 serves as an external interrupt pin. It goes LOW during an interrupt event, which is often used to notify the microcontroller that a certain condition or gesture has been detected. 

To wire the APDS-9960 sensor to a microcontroller, you would typically connect the following pins: -Connect VL (Pin 1) to a power supply (optional, if the PS jumper is not connected). 

-Connect GND (Pin 2) to the ground (GND) of your microcontroller. 

-Connect VCC (Pin 3) to the power supply voltage within the specified range. 

-Connect SDA (Pin 4) to the SDA pin on your microcontroller or I2C bus. 

-Connect SCL (Pin 5) to the SCL pin on your microcontroller or I2C bus. 

-Connect INT (Pin 6) to an available external interrupt pin on your microcontroller. 

With this wiring setup and the appropriate code, you can use the APDS-9960 sensor to detect and process RGB colors, ambient light levels, proximity, and gestures, making it a versatile sensor for various applications like touchless interfaces and color detection.

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/3D%20Model%20Top-Side.png)
Figure 3. Rough 3D Model of entire Robot

The figure above shows a rough 3D model of what the robot will look like with the Start Sensor System. In the picture above, the Green represents Power System, the blue represents the Navigation System, the Paint roller is the Button Push Mechanism, the Orange represents the Main Controller, the Yellow represents the Team Spirit System, the Brown stick on the back of the robot represents the Box Sweep System, and the Drivetrain is located underneath the robot. The start system includes both Gray rectangles near the back of the robot. The red marker is the push button, while the black marker is the color sensor, the breadboard has been omitted for clarity.
Figure 4. Precise Height of Start Sensor

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/3D%20Model%20Side.jpg)
Figure 4. Precise Height of Start Sensor

Figure 4 (above) shows the scale of how the Sensor and button will be located from a side view. You can see that the bottom of the sensor and button range from 3.7-4.3 inches due to the location of the Green LED placed on the course (Figures 6 & 7). The height of the tracks, once designed in the Drivetrain System, will adjust this height further, however the sensor must hit this range to properly read the green light that indicates the start of the run(Constaint 4).

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/3D%20Model%20Top.png)
Figure 5. Precise location of Start Sensor

Figure 5 (above) shows where the Sensor will lay out on the Robot and a rough location of the button. You can read more about the button location in the analysis section. 

## Analysis

Constraint 1 Solution:  The RGB Sensor shall detect the color green because we will set both sensors into a high state, which will allow it to only detect green. The description of how this works is in the Buildable Schematic Section.

Constraint 2 Solution: The RGB Sensor shall consider at least 4.0V as a HIGH signal and anything lower than 4.0V as a LOW signal. Per the datasheet for the RGB Sensor, the High-level input voltage is VDD = 2.7 V to 5.5 V and the minimum high-level is 2V and the max high-level is equal to VDD, which shall be 5V. The Low-level input voltage is VDD = 2.7 V to 5.5 V and the minimum low-level is 0V and the max low-level is 0.8V. This means that the RGB sensor’s control pins will be modified by either connecting them to the power provided (5V) or the ground for a high or low signal respectively. 

Constraint 3 Solution: The RGB Sensor is supposed to read and output in 3 seconds, if it does not, we will not get the points for that run of the competition. We will then use the push button start to allow our robot to start manually, allowing us to attempt other tasks for points. If we wait much longer than 3 seconds, we possibly lose out on points in other aspects of the competition. 

Constraint 4 Solution: The RGB Sensor will be located on the back, middle of the robot (Figure 3 & 5). This will ensure that the sensor has a close enough range to read the Green LED. The Green LED is located on the back beginning wall, like how figure 6 conveys. The Sensor shall be placed between 3.7 to 4.3 inches from the ground. This is because the Sensor is best at detecting between 0.0 to 0.8 inches away; however the LED cannot be read by the sensor if it is parallel with the LED due to potential blockage or shadows from the sensor itself. Placing it slightly down will allow more light to flow into the sensor. The B represents the location of the Green LED on the Competition Board. Figure 7 shows us the dimensions of the location of the Green LED so that we may place our RGB sensor appropriately.

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/Board%20Diagram.png)
Figure 6. Competition Board Layout  

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/Board%20Diagram%202.png)
Figure 7. Exact Height of Start Sensor

Constraint 5 Solution: The RGB sensor must be positioned in close proximity to the Green Light LED, with an optimal placement range of 0.5 inches. This confines the allowable distance to a 1-inch zone, ensuring the sensor captures the widest spectrum of green light for accurate detection.

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/CazBilbrey-StartSensor-SignOff/Documentation/Signoffs/Start%20Sensor/3D%20Model%20Top%202.png)
Figure 8. Exact location lengthwise of Start Sensor and green LED

Constraint 6 Solution: The RGB Sensor shall be located within a width range of the Green Light LED location. This width range would be around 3 inches from the wall to the middle of the sensor. In figure 6, you can see that the distance from the middle of the sensor to the end of the robot is 1.3 inches or 3.3 cm. This range is to keep it as close as possible to the Green LED so that the sensor may read the light and output like anticipated. 

## BOM

| Item | Description | Subsystem | Part Number | Manufacturer | Quantity | Price | Total Price |
|------|-------------|-----------|-------------|--------------|----------|-------|-------------|
| RGB Sensor | Sensor to detect green LED | Start Sensor System | APDS-9960 | Avago Technologies | 1 | $7.50 | $7.50 |
| Push Button (20 pcs) | Failsafe Button | Start Sensoir System | TS-D001, 5mm | CHANZON | 1 pk | $4.99 | $4.99 | 
| | | | | | | | $12.49 |