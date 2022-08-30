NOTES
* https://www.youtube.com/watch?v=isOekyygpR8
* MAX_Delay is like 50 days, by running HAL_UART_Transmit(&huart2, buf, strlen((char*)buf), HAL_MAX_DELAY); we say do it for like 50 days
* 7-bit, we need to shift our binary by one to left (0x48<<1)
* sensor should work with default config settings
* register bits are at zero, but it requires 2 bites read to get all 12 bits (page 16)
* start condition - SDA sends 1 - we know we communicate
* Then SDA sends the address (SCL are just clocks)
* Final bit of byte is read/write
* Next bit is acknowledge bit
* Next byte is the register address
* Next bit is acknowledge
* Then stop condition
* Then start condition
* Then adrress again, but with write
* Then 2 bytes of temperature data (acknowledge in middle)
* Last four bites are always zeros
* Last bit is 1 (NACK - master stops sequential read)
* Last is stop condition