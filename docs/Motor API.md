# PIC & Motor API

Effective communication between the ESP32, PIC18LF26K22, and BTM9011EPXUMA1 motor drivers requires well-structured message formats. These message structures ensure seamless data exchange for movement commands, SPI-based motor control, and speed feedback to the HMI.

---

## Movement Commands from ESP32 to PIC18LF26K22

This message structure represents movement commands sent from the ESP32 to the PIC18LF26K22. The `Data` byte encodes direction commands using simple integer values. Each byte is structured for clarity and consistency with UART communication standards.

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                                |
|----------|-------------------|---------------|----------------|----------------|--------------------|------------------------------------------------|
| 1        | Start              | `uint8_t`     | `0x41`         | `0x41`         | `0x41`             | Start byte identifier (ASCII 'A')              |
| 2        | Sender             | `uint8_t`     | `0x01`         | `0x04`         | `0x03`             | Address for ESP32                              |
| 3        | Receiver           | `uint8_t`     | `0x05`         | `0x05`         | `0x05`             | Address for PIC18LF26K22                        |
| 4        | Data               | `uint8_t`     | `0x00`         | `0x03`         | `0x01`             | Direction: 0 = Stop, 1 = Forward, 2 = Right, 3 = Left |
| 5        | End                | `uint8_t`     | `0x42`         | `0x42`         | `0x42`             | End byte identifier (ASCII 'B')                |

---

## SPI Communication between PIC18LF26K22 and BTM9011EPXUMA1

This structure defines a 16-bit SPI message between the PIC18LF26K22 and the BTM9011EPXUMA1 motor drivers. It enables control over motor behavior by assigning motor IDs, PWM values, and returning status flags for diagnostics.

| **Field**       | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                                  |
|-----------------|------------------|---------------|---------------|---------------|-------------------|--------------------------------------------------|
| 1               | command_word      | `uint16_t`    | `0x0000`       | `0xFFFF`       | `0x0A01`           | SPI command including motor control bits         |
| 2               | motor_id          | `uint8_t`     | `1`           | `2`           | `1`               | 1 = Left motor, 2 = Right motor                  |
| 3               | pwm_value         | `uint16_t`    | `0`           | `65535`       | `50000`           | PWM speed value                                  |
| 4               | status_flags      | `uint8_t`     | `0x00`         | `0xFF`         | `0x1F`             | Motor status and error flags                    |

---

## Speed Feedback from PIC18LF26K22 to ESP32

This message structure allows the PIC18LF26K22 to report motor direction or other feedback to the ESP32. It mirrors the same format as the movement command message for consistency.

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                                |
|----------|-------------------|---------------|----------------|----------------|--------------------|------------------------------------------------|
| 1        | Start              | `uint8_t`     | `0x41`         | `0x41`         | `0x41`             | Start byte identifier (ASCII 'A')              |
| 2        | Sender             | `uint8_t`     | `0x05`         | `0x05`         | `0x05`             | Address for PIC18LF26K22                        |
| 3        | Receiver           | `uint8_t`     | `0x01`         | `0x05`         | `0x03`             | Address for ESP32                               |
| 4        | Data               | `uint8_t`     | `0x00`         | `0x03`         | `0x01`             | Feedback: 0 = Stop, 1 = Forward, 2 = Right, 3 = Left |
| 5        | End                | `uint8_t`     | `0x42`         | `0x42`         | `0x42`             | End byte identifier (ASCII 'B')                |

