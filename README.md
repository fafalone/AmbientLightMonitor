# AmbientLightMonitor
## Ambient Light Sensor Monitor v1.1
Using ISensorManager and ISensor in twinBASIC to retrieve data from device sensors

![image](https://github.com/user-attachments/assets/e4f545f3-bfb7-409d-9580-e92a9e0e5f0b)


This is an example of how to get live raw data from the sensors found in many laptops and tablets. This app demonstrates that by reading data from the Ambient Light Sensor, but the technique is easily adapted to other sensors like accelerometers, gyroscopes, magnetometers, etc.

All the main action is wrapped in a class that's designed to be reusable; you just need to instantiate it, call Initialize, call Uninitialize when you're done, and it will raise an event each time the sensor data is updated. That can be many times per second, so in this example the list/log only takes samples at a certain interval.

Ambient light is measured in lux, which isn't linear so we use the Log to normalize it to a range for the progressbar. The maximum chosen came from this list on Wikipedia:

```
Illuminance (lux)     Surfaces illuminated by
0.0001            Moonless, overcast night sky (starlight) 
0.002             Moonless clear night sky with airglow 
0.05–0.3          Full moon on a clear night 
3.4               Dark limit of civil twilight under a clear sky 
20–50             Public areas with dark surroundings 
50                Family living room lights  
80                Office building hallway/toilet lighting 
100               Very dark overcast day 
150               Train station platforms 
320–500           Office lighting 
400               Sunrise or sunset on a clear day.
1000              Overcast day; typical TV studio lighting
10,000–25,000     Full daylight (not direct sun) 
32,000–100,000    Direct sunlight
```

**Requirements:** Windows 7 or newer

Based on the AmbientLightAware Windows SDK sample, but there are substantial design changes because of ATL templates, differences between C++ and tB classes, a desire to use regular tB Events, and other factors.

I thought this might be useful as an actual utility, so cleaned up the UI and added a few features to polish it; so the project repository has binary builds.

![image](https://github.com/user-attachments/assets/3641b330-7483-41ae-ba52-b852dc262386) ![image](https://github.com/user-attachments/assets/afc968cf-3302-4167-89cb-23a5f5d893b5)


**Changelog:**\
02 Mar 2025 - v1.1\
  -Added option to only log sample if above a given threshold\
  -Added About dialog command to system menu\
   -Arranged tab order logically.\
   -Updated manifest with support and trustinfo.
         
01 Mar 2025 - v1.0 - Initial release

## Made using twinBASIC

![339231410-abba1d5d-0adb-4b32-a0cb-0f43ad13f1e6](https://github.com/user-attachments/assets/8a585214-547e-4a39-a3a7-75a71514c6a3)

twinBASIC is a new language and IDE that's aiming for 100% backwards compatibility with Visual Basic 6.0 while adding a lengthy list of new language features and a modern IDE experience. It's currently under development but far enough along that it supports many large, complex apps. I'm a huge fan of the project and this app was made entirely using only tB.

[twinBASIC FAQs](https://github.com/twinbasic/documentation/wiki/twinBASIC-Frequently-Asked-Questions-(FAQs))

[twinBASIC Home Page](https://twinbasic.com)

[twinBASIC GitHub](https://github.com/twinbasic/twinbasic)

[twinBASIC Releases](https://github.com/twinbasic/twinbasic/releases)
