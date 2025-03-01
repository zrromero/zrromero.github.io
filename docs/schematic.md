# Motor Schematic

![image](https://github.com/user-attachments/assets/2c6c429d-e915-404e-9891-2c69c7c8217d)


[View PDF](https://github.com/zrromero/zrromero.github.io/blob/main/docs/images/EGR314MotorSystem.pdf)

[Download ZIP](https://github.com/zrromero/zrromero.github.io/blob/main/docs/images/EGR314_MotorSubsystem%20(2-21-2025%2011-43-22%20PM).zip)


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
