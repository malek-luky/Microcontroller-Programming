1) Push button set to external interrupt mode with rising edge
2) in NVIC enable [15:10] EXTI line interrupts + select for init sequence after code generation tab
3) prirority cn be set under GPIO->NVIC->Preemption Priority

NOTES
-interrupt handlign functions are in STM32f4xx_it.c (void EXTI15_10_IRQHandler(void))
-the HAL_GPIO_EXTI_IRQHandler(B1_Pin); in the fucntion mentioned above is preventing the interrupt from re-firing
-GPIO_InitStruct.Mode = GPIO_MODE_IT_RISING means it will create an interrupt when we go from 0->1 (aka press the button)