Troubleshooting
- if some of the led is not lighting, we reached the maximum PWM!!!
- in other words, we have to set up the PWM for each color to one third of total PWM
- if we set it up like 100% PWM for all colors, only one will shine!
- therefore changed to peroid 1962 and pulse 654

PROBLEM
-for some reason if I connect the led not every channel can work in parellel
-althought that the duty cycle is only 33% for each channel, so we dont reach the max value
-nevertheless, the duty cycle should be capable of running at 100% for all channels
-weird but I will pass it, no idea what is wrong, could be debugged using the analyzer