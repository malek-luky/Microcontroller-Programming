WE ARE USING Photoresistor
used pin PA4 (IN4) for ADC
Implemented Addon1 with green led, addon2 not implemented, but it would be done using interrupt handler
from the ADC, no big deal (maybe its kinda big deal xd)

VYPOCET Z RAW
mame 400-4095 (4095 je 0, 400 je 10)
chceme 0-10
-3695 -> 0 (nejdriv -4095 pak /-369.5)

VYPOCET DELAY
0 -> delay 1000
10 -> delay 100
prvne, mame -10->0, pak *-900, mame 900->0, pak +100 