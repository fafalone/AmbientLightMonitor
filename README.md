# AmbientLightMonitor
## Ambient Light Sensor Monitor v1.0

![image](https://github.com/user-attachments/assets/5e716aba-5308-4652-8373-8a73833b03cf)

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

**Changelog:**

01 Mar 2025 - v1.0 - Initial release
