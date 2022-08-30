EXERCISE 8
-working for both ST-Link UART and external UART

EXTERNAL UART
-co je co na usb kabelu lze najít v dokumentaci na obrazku TTL USB
-PC6 - UART6TX - RXD
-PC7 - UART6RX - TXD

Task 2
HCLK 84MHz
APB2 peripheral 84MHz

Task 6
USART_TX = PA2
USART_RX = PA3

Task 8
huart2.Instance = USART2;
huart2.Init.BaudRate = 9600;
huart2.Init.WordLength = UART_WORDLENGTH_8B;
huart2.Init.StopBits = UART_STOPBITS_1;
huart2.Init.Parity = UART_PARITY_NONE;
huart2.Init.Mode = UART_MODE_TX_RX;
huart2.Init.HwFlowCtl = UART_HWCONTROL_NONE;
huart2.Init.OverSampling = UART_OVERSAMPLING_16;

Troubleshooting
in case when the output is random shit, go to Project->Properties->C++ Build
->Settings -> MCU Settings ->check two box in bottom

Question 1
0.015625Mhz

Question 2
Nothing

Question 3
USART1 is on Peripheral clock 2 PCLK2 (high speed: 72MHz), while the other USART (2, 3, ...) are on Peripheral clock 1 PCLK1 (low speed: 36MHz).
Only USART1 can run at the maximum speed of 4.5Mbits/s. Other USART are limited to 2.25Mbits/s

Question 4
9th bit is used for mode set (or parity)?
9-bit UART mode is typically used to implement a 'single master/multiple slaves' bus scheme using the UART. In this scheme, a 9th bit is added to each transmitted byte between the MSB of the data byte and the STOP bit. This 9th bit indicates whether the preceeding 8-bits should be interpreted as 'address' or as 'data'. If the 9th bit is a '1', the preceeding 8-bits should be interpreted as an 'address' byte. If the 9th bit is a '0', then the preceeding 8-bits should be interpreted as a 'data' byte.

Question 5
Did we need the Nucleo RX to TX (PC) cable connection? -  the pinouts are common with that of the ST-LINK module for the first task
We set iy up for UART2 which communicates via the normal port, BUT
For the second and third exercise we use UART3, which communicates via the pins only
We need 4 cables (for gnd, 3v, tx, rx) for upcomming tassk)