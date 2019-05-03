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

## Porting:
Note on porting to Step-7, Codesys or similar:
```
    #VergangeneZeit := LREAL_TO_REAL(RUNTIME(#StaticZyklusZeit_Aux));
    IF #VergangeneZeit > 0 AND #VergangeneZeit < 0.1 THEN
```    
The first line returns the time between two calls in seconds. The resolution is accurate to the nanosecond. The second one checks the validity. With Step-7 I would pass the time as parameter, with Codesys TIME_TCK can be used. On 300 PLC it might be possible to work with "SFC64"(TIMETICK). 

## Open works
- Writing instructions
- Create sample projects
- Convert everything to English
- debugging
- Porting to different controllers

## License:
This project is released under the WTFPL LICENSE.
<a href="http://www.wtfpl.net/"><img src="http://www.wtfpl.net/wp-content/uploads/2012/12/wtfpl-badge-4.png" width="80" height="15" alt="WTFPL" /></a>
