When we want to use the interrupts, we have to enable the TIM1 update under NVIC, otherwise the interrupt
wont be visible when coutner rollover happens

Question 1
-Yes, it is working, as it is the function that handles all the interrupts (not exactly the rollout, but any other interrupt, for example when the clock stops working)
-But, using the HAL_TIM_PeriodElapsedCallback is better, as we have many other situatuin when we handle some other interrupt
-Using the function above ensures that the interrupt is triggered exactly at the rollover of this exact timer

This functions we can use for handling the interrupts:
• HAL_TIM_PeriodElapsedCallback()
• HAL_TIM_PeriodElapsedHalfCpltCallback()
• HAL_TIM_OC_DelayElapsedCallback()
• HAL_TIM_IC_CaptureCallback()
• HAL_TIM_IC_CaptureHalfCpltCallback()
• HAL_TIM_PWM_PulseFinishedCallback()
• HAL_TIM_PWM_PulseFinishedHalfCpltCallback()
• HAL_TIM_TriggerCallback()
• HAL_TIM_TriggerHalfCpltCallback()
• HAL_TIM_ErrorCallback()