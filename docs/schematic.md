# Motor Schematic

![image](https://github.com/user-attachments/assets/eb7b002d-44b1-409b-963b-1ff3df97e0ba)

[View PDF](https://github.com/zrromero/zrromero.github.io/blob/main/docs/images/EGR314MotorSystem.pdf))

[Download ZIP](https://github.com/zrromero/zrromero.github.io/blob/main/docs/images/EGR314_MotorSubsystem%20(2-21-2025%2011-43-22%20PM).zip)


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

## **Key Takeaways from the Power Budget Analysis**

### **1. The Power Supply Can Handle the Load**
- The estimated total power draw is **~12.47W**, with the **motors consuming the most power (~7.44W).**
- A **12V power supply** should provide at least **2.15A** (total estimated current draw).
- If the power supply is **under 2.5A**, the system may struggle under peak loads.

### **2. The Voltage Regulator Needs to Handle a Considerable Load**
- The **MIC4680-3.3YM** steps **12V down to 3.3V**, with **~80-90% efficiency**, meaning some power is lost as heat.
- Since it provides power to the **microcontroller and motor drivers**, it must supply **at least 0.5A**.
- **Heat dissipation (e.g., a heatsink)** might be necessary.

### **3. The Motors Are the Biggest Power Consumers**
- The **motors (HC385G-302)** each draw **0.31A at 12V**, consuming most of the power.
- If both motors **stall or run at peak load**, power draw **could be higher** than estimated.

### **4. The Motor Drivers Must Support the Load**
- The **DRV8830 motor drivers** support **up to 1A per channel**, which is **sufficient** for normal motor operation.
- At startup, motors may briefly exceed their rated current, requiring:
  - **Bulk capacitors** to prevent voltage dips.
  - **PWM control** to prevent excessive startup current draw.

### **5. The Microcontroller Uses Minimal Power**
- The **PIC18LF26K22** draws **only ~25mA at 3.3V**, consuming just **0.08W**.
- Its power consumption is negligible compared to the motors and drivers.

---

## **Conclusions & Recommendations**

### **1. Use a Power Supply with a Safety Margin**
- The estimated draw is **~2.15A**, so a **12V, 3A power supply** is recommended.
- If using a battery, it should provide **at least 2.5A continuously**.

### **2. Consider Heat Dissipation for the Voltage Regulator**
- The **MIC4680-3.3YM** will dissipate heat during step-down conversion.
- Ensure **good PCB layout, airflow, or a heatsink** if it gets hot.

### **3. Monitor Performance in Testing**
- If motors **stall often** or the regulator **overheats**, adjustments may be needed.
- **Current measurement during real-world testing** will confirm power budget estimates.
