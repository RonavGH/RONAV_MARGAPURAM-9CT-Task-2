# MECHATR0NICS PROJECT DOCUMENTATION 

# Requirements Definition: 

# Functional Requirements:
 
* **Power Detection & Alerts**: If the machine is turned on, the Blue LED also stays on (so that users are aware the alarm is powered).
* **Fire Detection & Alerts**: If the sensor values are above boundary (have yet to determine), Red LED turns on and buzzer continously buzz.
* **Neutral and Warning Alerts**: If the sensor values are within the boundary, Green LED is activated and remains on. If the sensor values are within but less than 2 degrees/values off the boundary, a Yellow LED turns on and the buzzer starts buzzing off and on repeatedly.

# Unfunctional Requirements:

# PSEUDOCODE FOR ALGORITHM

START

Initialise smoke sensor
Initialise green LED
Initialise red LED
Initialise buzzer

LOOP forever

    Read smoke level

    IF smoke level > threshold THEN
        Turn green LED OFF
        Turn red LED ON
        Turn buzzer ON
    ELSE
        Turn green LED ON
        Turn red LED OFF
        Turn buzzer OFF
    ENDIF

    Wait 0.1 seconds

END LOOP