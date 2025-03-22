# Message Structures for PIC18LF26K22 Communication

Effective communication between the ESP32, PIC18LF26K22, and the BTM9011EPXUMA1 motor drivers requires well-structured message formats. These message structures ensure seamless data exchange for movement commands, motor control via SPI, and speed feedback to the HMI.

## Movement Commands from ESP32 to PIC18LF26K22

The first message structure involves movement commands from the ESP32 to the PIC18LF26K22. This message includes a type identifier, a direction byte, and a speed level byte. The message type byte distinguishes movement commands from other message types. Direction values (0 for Stop, 1 for Left, 2 for Right, and 3 for Straight) are limited to four states for efficiency. The speed level byte ranges from 0 to 100, representing the speed percentage.

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                                |
|----------|-------------------|--------------|--------------|--------------|------------------|------------------------------------------------|
| 1        | message_type      | uint8_t      | 1            | 1            | 1                | Message type identifier for movement           |
| 2        | direction         | uint8_t      | 0            | 3            | 2                | 0=Stop, 1=Left, 2=Right, 3=Straight            |
| 3        | speed_level       | uint8_t      | 0            | 100          | 75               | Speed percentage (0-100%)                      |

## SPI Communication between PIC18LF26K22 and BTM9011EPXUMA1

The second message structure is tailored for SPI communication between the PIC18LF26K22 and the BTM9011EPXUMA1 motor driver. SPI requires a 16-bit command word that dictates the operation type. The motor ID byte indicates which motor is being controlled (left or right). The PWM value is a 16-bit number allowing precise speed adjustments, while status flags give quick feedback on motor states and error detection.

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                               |
|----------|------------------|--------------|--------------|--------------|------------------|------------------------------------------------|
| 1        | command_word      | uint16_t     | 0x0000       | 0xFFFF       | 0x0A01           | SPI command word including control bits        |
| 2        | motor_id          | uint8_t      | 1            | 2            | 1                | 1 = Left Motor, 2 = Right Motor                |
| 3        | pwm_value         | uint16_t     | 0            | 65535        | 50000            | PWM value for motor speed (0-65535)            |
| 4        | status_flags      | uint8_t      | 0            | 255          | 0x1F             | Status flags for feedback and error states      |

## Speed Feedback from PIC18LF26K22 to ESP32

The final message structure covers speed feedback from the PIC18LF26K22 to the ESP32. This feedback is essential for performance monitoring and includes a message type byte, motor ID, speed value in RPM, and an error flag. The message type ensures correct handling by the ESP32. The speed value is capped at 5000 RPM to match the expected motor limits. The error flag (0 for No Error, 1 for Error) simplifies error detection.

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                                |
|----------|------------------|--------------|--------------|--------------|------------------|------------------------------------------------|
| 1        | message_type      | uint8_t      | 3            | 3            | 3                | Message type for speed feedback                |
| 2        | motor_id          | uint8_t      | 1            | 2            | 1                | 1 = Left Motor, 2 = Right Motor                |
| 3        | speed_value       | uint16_t     | 0            | 5000         | 2750             | RPM of the motor                               |
| 4        | error_flag        | uint8_t      | 0            | 1            | 0                | 0 = No Error, 1 = Error Detected               |

## General Handling Considerations

- All messages must fit within the specified protocol (bytes 4-61) as per the overarching system message structure.
- Messages must be checked for proper framing, correct message type, and adherence to byte limits.
- Malformed or out-of-bound messages must be ignored.
- Every received message must be acknowledged or logged.

This structured approach ensures consistency across systems, enabling reliable and verifiable communication between the PIC18LF26K22, motor drivers, and ESP32 HMI feedback system.

