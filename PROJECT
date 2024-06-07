## AUTOMATED SMS CALLS USING VSDSQUADRON MINI and SIM800L MODULE




![image](https://github.com/mreddybalaji/VSDSquadron-Research-Internship/assets/130784457/3893de24-400e-4c67-9bc7-ae26d541c592)



### VSDSQUADRON MINI and SIM800L Pin Connections

#### VSDSQUADRON MINI Pin Description:
1. **5V**: Power supply pin that provides 5V to the connected module.
2. **GND**: Ground pin for common ground reference.
3. **PA10**: General-purpose I/O pin, used as the TX (Transmit) pin for UART communication.
4. **PA9**: General-purpose I/O pin, used as the RX (Receive) pin for UART communication.

#### SIM800L Pin Description:
1. **VCC**: Power input pin for the SIM800L module, typically requires 3.7-4.2V but is connected to the 5V pin of VSDSQUADRON MINI in this case.
2. **GND**: Ground pin, connected to the common ground.
3. **TXD**: Transmit pin for UART communication, connected to PA10 of the VSDSQUADRON MINI.
4. **RXD**: Receive pin for UART communication, connected to PA9 of the VSDSQUADRON MINI.

### Code Implementation:

The provided code initializes the VSDSQUADRON MINI microcontroller and communicates with the SIM800L GSM module to send an SMS.

1. **Includes and Defines**:
   - `#include <ch32v00x.h>`: Includes the header file for the VSDSQUADRON MINI microcontroller.
   - `#include <debug.h>`: Includes the debug header for debugging purposes.
   - `#define SIM800L_UART USART1`: Defines the UART port used for communication with the SIM800L.
   - `#define SIM800L_BAUDRATE 9600`: Defines the baud rate for UART communication.

2. **Delay Functions**:
   - `void Delay_Init(void)`: Initializes delay functions (implementation needed if required).
   - `void Delay_Ms(uint32_t n)`: Delays for `n` milliseconds by executing a loop.

3. **USART Initialization and Communication Functions**:
   - `void USART_Printf_Init(uint32_t baudrate)`: Initializes the USART peripheral with the specified baud rate.
   - `void USART_SendString(USART_TypeDef* USARTx, char* str)`: Sends a string over the specified USART.

4. **Setup Function**:
   - Initializes the system clock and delay functions.
   - Configures the USART for communication with the SIM800L.
   - Sends AT commands to the SIM800L to send an SMS to the specified phone number.

5. **Main Function**:
   - Calls the `setup()` function and enters an infinite loop.

### Connections Summary:

```plaintext
+-----------------+      +----------+
| VSDSQUADRON MINI|      | SIM800L  |
|                 |      |          |
|              5V |------| VCC      |
|             GND |------| GND      |
|             PA10|------| TXD      |
|             PA9 |------| RXD      |
+-----------------+      +----------+
```

### Usage:

- Connect the pins of the VSDSQUADRON MINI to the SIM800L as described.
- Enter the phone number to which the SMS or call.
- Compile and upload the code to the VSDSQUADRON MINI microcontroller.
