# **Schematic & PCB**
[Download ZIP](images/EGR314_MotorSubsystem (5-5-2025 4-15-22 PM).zip)

## **Schematic Design**
![SystemSchematic](images/EGR314MotorSystem.pdf)

[View PDF](images/EGR314MotorSystem.pdf)

## **PCB**
### **PCB Design**
![PCBTop](docs/images/PCBDesignTOP.png)
![PCBBottom](docs/images/PCBDesignBOTTOM.png)

### **Final PCB**
![PCBFront](docs/images/MOTORPCBFRONT.png)
![PCBBack](docs/images/MOTORPCBBACK.png)

[Download Gerber Files](docs/images/PCB.zip)

## **Schematic Functionality**
Blah Blah Blah

## **Version 2.0**
How we would update/change the design in future

# Power Budget
## Power Budget Table

| **Component**                           | **Power Consumption**       | **Voltage**     | **Current (Amps)** | **Power (W)**       | **Notes**                                               |
|-----------------------------------------|-----------------------------|-----------------|--------------------|---------------------|---------------------------------------------------------|
| **HC385G-302 Motor 1**                 | 12V DC Motor                | 12V             | 0.31A              | 3.72W               | Rated at 12V, 0.31A motor                                 |
| **HC385G-302 Motor 2**                 | 12V DC Motor                | 12V             | 0.31A              | 3.72W               | Same as Motor 1                                           |
| **BTM9011EPXUMA1 Motor Driver 1**      | Motor Driver                | 12V (Motor)     | ~0.02A (standby)    | 0.24W               | Approximate power for low load; higher at full load    |
| **BTM9011EPXUMA1 Motor Driver 2**      | Motor Driver                | 12V (Motor)     | ~0.02A (standby)    | 0.24W               | Approximate power for low load; higher at full load    |
| **MIC4680-3.3YM Voltage Regulator**   | Step-Down Regulator         | 14.8V (Input)   | 0.35A (for 3.3V load) | 1.16W               | Power consumed based on 3.3V conversion                |
| **PIC18LF26K22 Microcontroller**       | MCU                         | 3.3V            | 0.04A              | 0.13W               | Low current consumption (approx. 40mA)                 |
| **Total Power Consumption**            |                             |                 |                    | **9.49W**            |                                                         |
