# Message Structures for PIC18LF26K22 Communication

Effective communication between the ESP32, PIC18LF26K22, and the BTM9011EPXUMA1 motor drivers requires well-structured message formats. These message structures ensure seamless data exchange for movement commands, motor control via SPI, and speed feedback to the HMI.

## Movement Commands from ESP32 to PIC18LF26K22

The first message structure involves movement commands from the ESP32 to the PIC18LF26K22. The message type byte determines movement commands. Direction values (0 for Stop, 1 for Left, 2 for Right, and 3 for Straight) are limited to four states for efficiency.

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                                |
|----------|-------------------|--------------|--------------|--------------|------------------|------------------------------------------------|
| 1        | Start             | uint8_t      | 0X41         | 0x41          | N/A             | Message type identifier for movement           |
| 2        | Sender            | uint8_t      | 0x03         | 0x03          | N/A             | Adress for ZR                                  |
| 3        | Receiver          | uint8_t      | 0x01         | 0x04          | 0x03            | Who needs to receive message                   |
| 4        | Data              | uint8_t      | 0X00         | 0x03          | 1               | 0=Stop, 1=Left, 2=Right, 3=Straight            |
| 5        | End               | uint8_t      | 0x42         | 0x42          | N/A             | N/A                                            |


## SPI Communication between PIC18LF26K22 and BTM9011EPXUMA1

The second message structure is tailored for SPI communication between the PIC18LF26K22 and the BTM9011EPXUMA1 motor driver. SPI requires a 16-bit command word that dictates the operation type. The motor ID byte indicates which motor is being controlled (left or right). The PWM value is a 16-bit number allowing precise speed adjustments, while status flags give quick feedback on motor states and error detection.

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                               |
|----------|------------------|--------------|--------------|--------------|------------------|------------------------------------------------|
| 1        | command_word      | uint16_t     | 0x0000       | 0xFFFF       | 0x0A01           | SPI command word including control bits        |
| 2        | motor_id          | uint8_t      | 1            | 2            | 1                | 1 = Left Motor, 2 = Right Motor                |
| 3        | pwm_value         | uint16_t     | 0            | 65535        | 50000            | PWM value for motor speed (0-65535)            |
| 4        | status_flags      | uint8_t      | 0            | 255          | 0x1F             | Status flags for feedback and error states      |

## Speed Feedback from PIC18LF26K22 to ESP32

The final message structure covers speed feedback from the PIC18LF26K22 to the ESP32. 

| **Byte** | **Variable Name** | **Data Type** | **Min Value** | **Max Value** | **Example Value** | **Description**                                |
|----------|-------------------|--------------|--------------|--------------|------------------|------------------------------------------------|
| 1        | Start             | uint8_t      | 0X41         | 0x41          | N/A             | Message type identifier for movement           |
| 2        | Sender            | uint8_t      | 0x03         | 0x03          | N/A             | Adress for ZR                                  |
| 3        | Receiver          | uint8_t      | 0x01         | 0x04          | 0x03            | Who needs to receive message                   |
| 4        | Data              | uint8_t      | 0X00         | 0x03          | 1               | 0=Stop, 1=Left, 2=Right, 3=Straight            |
| 5        | End               | uint8_t      | 0x42         | 0x42          | N/A             | N/A                                            |

