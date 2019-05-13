# PID controller for Siemens SCL Tia-Portal

## Problem:
I always had a lot to do with control technology at the Tia Portal and was simply never satisfied with the Siemens modules. I need PI controllers for pressure control and PID for temperature control. Here are a few points that bothered me:
- Different devices among different CPUs use deferent lib.
- Cannot be simulated.
- Not posible to read the source and change it.
- Far too complicated with a high level of familiarisation.
- No portability to Codesys.
- Too high integration in TIA.
- Do a lot of tinkering and testing until finally something worked.
- Cyclic OBs and Global DB were absolutely necessary. You can not integrate it in your privat functions.
- Many thousands of pages of manuals.

## Work:
After a long search I did not find an alternative. But with OSCAT as an inspiration, since it is actually quite simple, I rewrote the functions. I wrote it in TIA14 and 15 for the 1200 and 1500 CPU. Now I have everything in productive use and wanted to see what you think about it. My intention was not to make everyone happy, but to give something back. I learned a lot thanks to open libs (OSCAT) and it wouldn't be right if I don't share back.

## Using instruction

The controller produce a outputs from 0 to 100. If used with a binary actor you shoud use the clock generator for pulse width modulation. The PI controller is disigned to run alone. Usefull for pressure regulation. The controller should alwasys stoped with the reset input is the regulation loop is disturbed. This prevents the integral to windup. 

- ir_Input = The mesuered value of pressure or themperature
- ir_Setpoint = The demanded value of pressure or themperature
- ir_ProportionalGain = The proportional gain, a tuning parameter
- ir_IntegrationGain = the integral gain, a tuning parameter
- ir_DifferentialGain = the derivative gain, a tuning parameter
- itime_DifferezialActionTime = the length of the derivative action, a tuning parameter
- ib_Reset = empty the integral and sets the output to zero
- or_Output = output value in % from 0 to 100

![PID Bild](https://github.com/OttoMeister/Siemens-Tia-Portal-PID-Controller/blob/master/PID-Control.png)

## Porting:
Note on porting to Step-7, Codesys or similar:
```
#PastTime := LREAL_TO_REAL(RUNTIME(#StaticCycleTime_Aux));
IF #PastTime > 0 AND #PastTime < 0.1 THEN
```    
The first line returns the time between two calls in seconds. The resolution is accurate to the nanosecond. The second one checks the validity. With Step-7 I would pass the time as parameter, with Codesys TIME_TCK can be used. On 300 PLC it might be possible to work with "SFC64"(TIMETICK). 

## Open works
- Writing instructions
- debugging
- Porting to different controllers

## License:
This project is released under the WTFPL LICENSE.
<a href="http://www.wtfpl.net/"><img src="http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-4.png" width="80" height="15" alt="WTFPL" /></a>
