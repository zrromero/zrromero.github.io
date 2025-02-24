# Motor Schematic

![image](https://github.com/user-attachments/assets/eb7b002d-44b1-409b-963b-1ff3df97e0ba)


# Power Budget
## Power Budget Table

| Component                          | Voltage (V) | Current (A) | Power (W) |
|------------------------------------|------------|------------|----------|
| **Power Source**                   | 12V        | ?          | ?        |
| **Motors (HC385G-302) x2**         | 12V        | 0.31A each | 7.44W   |
| **Motor Drivers (DRV8830DGQR) x2** | 3.3V-6.8V  | 1A max     | ~3.3W   |
| **Voltage Regulator (MIC4680-3.3YM)** | 12V → 3.3V | ~0.5A max | ~1.65W  |
| **Microcontroller (PIC18LF26K22)** | 3.3V       | ~25mA      | ~0.08W  |
| **Estimated Total Power**          | -          | ~2.15A     | ~12.47W |

