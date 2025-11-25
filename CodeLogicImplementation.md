# V. CODE LOGIC IMPLETMENATION
The program is written in Arduino IDE to control the Raspberry Pi Pico for gas and fire detection. The MQ-2 smoke sensor is connected to an analog pin (GP26), the flame sensor to a digital pin (GP2), and the buzzer to GP5. The code begins by setting these pins as inputs or outputs and starting serial communication for monitoring.

Inside the main loop, the Pico continuously reads the smoke level from the MQ-2 and the fire status from the flame sensor. The smoke reading is compared with a fixed threshold value to decide whether smoke is present. The flame sensor gives a LOW signal when fire is detected. If either smoke or fire is detected, the buzzer is turned ON to alert the user; otherwise, the buzzer remains OFF. This checking process repeats continuously, ensuring real-time monitoring and instant alert generation.


The system works on the principle that each sensor produces specific output values under different environmental conditions.
The fire–smoke detection system works by continuously monitoring the outputs of two sensors:

The flame sensor (digital output) gives:
- 1 → Flame detected
- 0 → No flame

The smoke sensor (analog output) gives:
- High value (>800) → Smoke detected
- Low value (<800) → No smoke

Based on the combination of both sensor readings, the system identifies four possible scenarios.

1 Case 1: No Flame, No Smoke
- The flame sensor output is LOW (0) and the smoke sensor value is below the threshold.
- This means no flame and no smoke are present.
- The system displays “System Normal!!!” and the buzzer remains OFF.

2 Case 2: Flame Detected, No Smoke
- The flame sensor gives HIGH (1) indicating flame is detected and the smoke sensor value is still below the smoke threshold.
- This means only flame is present without smoke.
- The system shows “ALERT: FLAME DETECTED!” and the buzzer turns ON.

3 Case 3: No Flame, Smoke Detected
- The flame sensor output is LOW (0) meaning no flame. The smoke sensor value is above the threshold, indicating smoke.
- This means only smoke is detected.
- The system shows “ALERT: SMOKE DETECTED!” and the buzzer turns ON.

4 Case 4: Both Flame and Smoke Detected
- The flame sensor gives HIGH (1) and the smoke sensor value is above the threshold.
- This means fire is present and smoke level is high, indicating a more dangerous situation.
- The system displays “WARNING: FIRE + SMOKE DETECTED!” and activates the buzzer ON with priority.
