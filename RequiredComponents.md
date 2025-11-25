# III. REQUIRED COMPONENTS TO DEVELOP SOLUTION
# 1. Hardware Components

1. Raspberry Pi Pico
- Acts as the main microcontroller.
- Handles sensor reading, decision-making, and output control.
- Programmed using Arduino IDE with Pico support package.

2. MQ-2 Gas/Smoke Sensor
- Used to detect smoke, LPG, propane, and general air-quality changes.
- Output type: Analog (Aout pin).
- Connected to Pico ADC pin (GP26/ADC0).

3. Flame/Fire Sensor (IR Flame Sensor Module)
- Detects flame presence using IR light spectrum.
- Output type: Digital (DO pin).
- Connected to a GPIO pin (GP22).

4. Active Buzzer
- Used to generate alert sound when fire/smoke is detected.
- Output type: Digital.
- Connected to GP15.

5. Jumper Wires ( Male-to-Female)
- Used for prototype wiring on a breadboard.

6. Breadboard
- For mounting components and making temporary connections.

7. USB Cable (Micro-USB)
Provides:
- Power supply to Raspberry Pi Pico
- Serial communication with Arduino IDE
- Program uploadin    


# 2. Software Requirements

1. Arduino IDE (Version 2.3.6)
- Used to write, compile, and upload code to Raspberry Pi Pico.
- Supports C/C++ programming.
- Required Board Support Package:
      Raspberry Pi RP2040 Boards.
