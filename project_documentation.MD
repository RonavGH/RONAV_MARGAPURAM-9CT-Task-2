# MECHATR0NICS PROJECT DOCUMENTATION 

# Requirements Definition: 

 ** Include the flowchart of my smoke detector **

# Functional Requirements:
 
* **Power Indicator**: When the smoke detector is switched on, the blue LED remains on to indicate the system has power.
Safe Condition: When the smoke sensor reading is below the warning threshold, the green LED remains on and the buzzer is off.
* **Warning Condition**: When the smoke sensor reading is within 2 units below the danger threshold, the yellow LED flashes and the buzzer sounds intermittently (0.5 seconds on, 0.5 seconds off).
* **Danger Condition**: When the smoke sensor reading is equal to or above the danger threshold, the red LED flashes continuously and the buzzer sounds continuously.
* **False Alarm Button**: When the mute button is pressed during a danger condition, the buzzer is muted for 20 seconds while the red LED continues flashing. After 20 seconds, if smoke is still detected, the buzzer resumes.
Button Cooldown: After the mute button has been used, it cannot be used again for 60 seconds.

# Unfunctional Requirements:

* **Response Time**: The machine should respond as quick as possible without compromising the functionality of the code. Every 100-400 milliseconds is the approximate reaction of the smoke detector, when it detects certain amounts of smoke or heat in the vicinity.
* **False Alarm Button**: In case of a false alarm, a button can be pressed that will mute the machine for 20 seconds. If it still keeps detecting flames, it will continue buzzing after the 20 seconds. There would be a one minute cooldown between button presses (meaning 40 seconds of true fire alerts with buzzing between them), and the Red LED will still continue flashing throughout the false alarm.


# PSEUDOCODE FOR ALGORITHM

START

INITIALISE ON Blue LED

SET warning threshold
SET danger threshold
SET mute timer to 0
SET cooldown timer to 0

WHILE smoke detector is ON

    READ smoke sensor value

    IF smoke sensor value >= danger threshold THEN

        Turn OFF Green LED
        Turn OFF Yellow LED

        IF mute timer = 0 THEN
            Turn ON Red LED
            Turn ON buzzer
        ELSE
            Turn ON Red LED
            Turn OFF buzzer
        END IF

        IF mute button is pressed AND cooldown timer = 0 THEN
            SET mute timer to 20 seconds
            SET cooldown timer to 60 seconds
        END IF

    ELSE IF smoke sensor value >= (danger threshold - 2) THEN

        Turn OFF Green LED
        Turn OFF Red LED 

        Flash Yellow LED
        Buzz intermittently
        Wait 0.5 seconds

        Turn OFF Yellow LED
        Turn OFF buzzer
        Wait 0.5 seconds

    ELSE

        Turn ON Green LED
        Turn OFF Yellow LED
        Turn OFF Red LED
        Turn OFF buzzer

    END IF

    IF mute timer > 0 THEN
        Decrease mute timer
    END IF

    IF cooldown timer > 0 THEN
        Decrease cooldown timer
    END IF

    WAIT 100–400 milliseconds (ms)

END WHILE

END