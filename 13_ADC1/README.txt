WE ARE USING TMP36
used pin PA5 (IN5) for ADC

All the statements Within the code snippet are discussed below:
- HAL_ADC_Start(&hadc:1) ;—Starts the ADC1 internal peripheral.
- HAL_ADC_PollForConversion(&hadc1, 100) ;—Waits for an end-0f-
conversion (EOC) signal before proceeding to the next instruction. The
100 value is the maximum time in milliseconds to wait for the EOC signal.
This is a blocking type instruction.
- raw = (double) HAL_ADC_GetValue(&hadc1) ;—Transfer the value from
the adc output register to the raw variable. This is a 12-bit value with a
maximum numerical value of 4095, which is roughly equivalent to 5 V.
The value is also cast to a double format.
- raw = raw * 0 . 452 ;—Conversion from a raw count to an absolute mV
output. The scaling factor 0.452 was determined using a precision voltage
measurement.
- value = (raw - 500 . 0)/1o ;—The raw mV value is converted to a °C
temperature using the TMP36 equation.
- value = (9*value)/5 + 32 ;—Classic equation to convert from °C to °F.
- sprintflmsg, ”%f\r\n”, value) ;—Causes the double variable value to
be converted to a string with a carriage return and line feed concatenated to
the value.
- HAL_UART_Transmit (&huart2, (uint8_t*) msg, 20, 100) ;—Performs
the actual transmission of the data from the MCU to the terminal program
- HAL_Delay(1000) ;—Inserts a one second delay between samples.