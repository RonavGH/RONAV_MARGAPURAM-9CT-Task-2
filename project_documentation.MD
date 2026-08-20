# FLAME SENSOR PROJECT DOCUMENTATION 

# Requirements Definition: 

 ** 

# Functional Requirements:
 
* **Detect Flames**: The system must detect the presence of flames in the vicinity using a flame sensor.

* **Measure flame intensity**: The sensor must send out a signal that represents the detected flame

* **Trigger an alert**: When a flame is detected, the system produce a flickering yellow light and displays a text message, alerting the user that flames have been detected in the vicinity.

* **Send data to the Pico**: The flame sensor must send its readings to the Raspberry Pi Pico for processing.

* **Safe Level**: When no presence of flame is detected, the system doesnt produce a flickering yellow light, displaying that the status is safe.

# Unfunctional Requirements:

* **Response Time**: The machine should respond as quick as possible without compromising the functionality of the code. Every 100-400 milliseconds is the approximate reaction of the flame sensor system, when it detects the presence of flames in the vicinity.

* **False Alarm Reduction**: The system should minimise false alarms caused by small changes in sensor readings or in normal environmental light.

* **Ease of system use**: The LED alerts should be clear enough that a user can immediately understand the system's current status.

* **Safety warnings**: The system should provide an immediate warning to the user when the presence of flame is detected and should not rely on the user to monitor the sensor reading.

# PSEUDOCODE FOR ALGORITHM

Start

Set flame sensor (GP16) as input
Set onboard LED as output
Print "Flame Sensor Active"

loop forever

    Read the flame sensor

    If flame is detected then
        Print "WARNING: Flame Detected!"
        Turn the onboard LED on
    Else
        Print "Status: Safe"
        Turn the onboard LED off
    End If

    Wait 0.5 seconds

End loop

Code for the flame sensor project:

import machine
import time

# Configure the digital flame sensor
# D0 of the flame sensor is connected to GP16
Flame_Digital = machine.Pin(16, machine.Pin.IN)

# Configure the Raspberry Pi Pico's onboard LED as an output
# The LED will turn on when a flame is detected
Onboard_Led = machine.Pin("LED", machine.Pin.OUT)

print("--- Flame Sensor Active ---")

while True:
    # Check the digital output of the flame sensor
    # The sensor outputs 1 (HIGH) when a flame is detected
    if Flame_Digital.value() == 1:
        # Display a warning message in the Shell
        print("WARNING: Flame Detected!")

        # Turn the onboard LED ON
        Onboard_Led.value(1)

    else:
        # Display a safe status message in the Shell
        print("Status: Safe")

        # Turn the onboard LED OFF
        Onboard_Led.value(0)

    # Wait for 0.5 seconds before checking the sensor again
    # This controls how frequently the sensor is checked
    time.sleep(0.5)

PEER EVALUATION
Evaluator 1: Fayaaz:

Plus - Achieves it's desired function, wiring doesn't seem very cluttered or messy. The LED system allows users to understand how the machine works very well.

Minus - Some issues with wiring and the functional requirements are slightly different to the new design.

Implication - The creator has added a lot of new additions to the initial machine. These additions do improve the acessibility of the machine, but also make it so that it doesn't follow the functional requirements completely and it has made wiring harder for the creator.

ALSO RONAV U NEED TO INCLUDE FLOWCHART FOR THE ALGORITHMS OTHERWISE YOU WILL LOSE MARKS!!!

Evaluator 2: Michael K:

Plus - The flame detection system works with clean code, very optimised and simple to follow. - The flame detection system outputs on multiple LEDs allowing me to see whether their is a flame or not.

Minus - The flame detections system output is kind of pointless, only alerting via light, which kind of defeats the purpose when you can see the flame.

Implication - The system allows the user to detect whether there is a flame within the vicinity. I would suggest adding a buzzer to improve on.

ALSO RONAV U NEED TO INCLUDE FLOWCHART FOR THE ALGORITHMS OTHERWISE YOU WILL LOSE MARKS!!!



