---
title: Solar Tracker Sensor
project_name: Solar Tracker Sensor
# image: /images/placeholder.svg
repository: https://github.com/anttronics/SolarTrackerSensor
issues: https://github.com/anttronics/SolarTrackerSensor/issues
stage: alpha
---
A simple sensor circuit that uses photo-transistors and boolean logic to indicate if a solar panel is pointing straight at the sun. It supports limit switches, has auto-parking logic, adjustable sensitivity and part of the PCB forms the shadow-casting part of the sensor.

### Outputs 
- It produces 4 digital outputs to indicate if movement is required in up, down, left or right directions. Those outputs can be passed directly to a motor controller which can correct the mis-alignment. 
- It also produces horizontal, vertical and combined "busy" signals to allow independent, as well as overall enabling/disabling of the motors.

**Warning**: All outputs are unprotected, digital signal outputs and should not be used to drive any motors directly.

### Limit Switches
It has normally-closed (NC) limit switch inputs for all 4 directions, but requires at least the "east" and "down" switches for auto-parking to function. The "west" and "up" limit switches can be omitted/bypassed if the motion mechanism has sufficient range and/or limits implemented elsewhere.

### Auto-parking
When the ambient light level falls below the adjustable threshold, it will auto-park the panel in the "east" and "down" position. Without the auto-park function, in the summer months, the panel would be left pointing west at sunset. The sun would then rise behind the panel and tracking would not resume until late morning, when the sun moves n front of the panel again.

### Sensitivity
A common reference level for all 4 comparators is produced using a potentiometer as a voltage divider. The simplest way to set the sensitivity is to adjust it on a dark cloudy day, to a level just above the parking level. This way it won't try to auto-park the panel every time a cloud moves across the sun. 

### Assembly
The board is designed in 3 parts: 
- the "logic" part which contains all the main components,
- the "sensor" part which contains the photo-transistors and
- the "shield" parts. 

The "sensor" board has the same footprints on both sides, allowing assembly on the "N" or "S" side, depending on whether the sun will be tracked from the north or south hemisphere.

It can be separated from the "logic" board and connected with wires, or it can be kept attached to the "logic" board. The traces between the boards complete all the required connections between the two boards.

The "shield" parts, when soldered onto the "sensor" board, form a pyramid-shaped sun screen that cast a shadow on the photo-transistors when the panel is not correctly aligned.

### Power supply
Even though all the components on the board could handle a higher voltage, a stable 5V DC power supply is highly recommended to ensure the reference levels for the comparator are actually effective. 

### Future ideas
- Motor control board with sleep/periodic wake-up function for low power consumption
- Battery charging board with constant panel voltage or MPP tracking.

### How did we get here?
The prototype "ancestor" of this board has been keeping an A4-size 4V panel pointed at the sun through my office window for a few years already. It charges a 2S LiPo battery during the day which in turn is used as a power bank to charge my phone. 

The mechanical construction is showing its age and needs an overhaul. The plan is to switch from continuous rotation servos to DC gear motors for smoother movement and in the process, try to tidy up the electronics as well.
