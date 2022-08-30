Default template from SME32CubeMX with custom PIN configuration
-only pin for green led and debugging is activated

Exercise 1
-wait is implemented using time and while(time>500) cycle

Exercise 2
-it will do the same thing even with different definition
-depends on what we prefer?
-it is defines in main.h

Exercise 3
-HAL_GPIO_WritePin()

Exercise 5
-find the pin name in gpio.c and then the #define in main.h

Notes
-we will use the GPIO if we connect to it externally to know which pin it is
-otherwise (e.g. for the led on processor) we can use only the LD2_Pin and LD2_GPIO_Port