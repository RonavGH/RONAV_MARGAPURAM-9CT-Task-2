# FLAME SENSOR PROJECT DOCUMENTATION 

# Requirements Definition: 
flowchart: [Click here to view Flowchart]()![alt text](<ronav flowchart coding official.svg>)


# Functional Requirements:
 
* **Detect Flames**: The system must detect the presence of flames in the vicinity using a flame sensor.

* **Measure flame intensity**: The sensor must send out a signal that represents the detected flame

* **Trigger an alert**: When a flame is detected, the system produce a flickering yellow light and displays a text message, alerting the user that flames have been detected in the vicinity.

* **Send data to the Pico**: The flame sensor must send its readings to the Raspberry Pi Pico for processing.

* **Safe Level**: When no presence of flame is detected, the system doesnt produce a flickering yellow light, displaying that the status is safe.
# Unfunctional Requirements:

* **Response Time**: The machine should respond as quick as possible without compromising the functionality of the code. Every 100-400 milliseconds is the approximate reaction of the flame sensor system, when it detects the presence of flames in the vicinity.

* **False Alarm Reduction**: The system should minimise false alarms caused by small changes in sensor readings or in normal environmental light.

* **Ease of system use**: The LED and buzzer alerts should be clear enough that a user can immediately understand the system's current status.

* **Safety warnings**: The system should provide an immediate warning to the user when the presence of flame is detected and should not rely on the user to monitor the sensor reading.

# PSEUDOCODE FOR ALGORITHM

Start

Set flame sensor (GP16) as input
Set onboard LED as output
Print "Flame Sensor Active"

Loop forever

    Read the flame sensor

    If flame is detected then
        Print "WARNING: Flame Detected!"
        Turn the red LED on
    Else
        Print "Status: Safe"
        Turn the green LED on
    End If

    Wait 0.5 seconds

End Loop

# PEER EVALUATION

**Evaluator 1: Fayaaz**:

*Plus* - Achieves it's desired function, wiring doesn't seem very cluttered or messy. The LED system allows users to understand how the machine works very well.

*Minus* - Some issues with wiring and the functional requirements are slightly different to the new design.

*Implication* - The creator has added a lot of new additions to the initial machine. These additions do improve the acessibility of the machine, but also make it so that it doesn't follow the functional requirements completely and it has made wiring harder for the creator.


**Evaluator 2: Michael K**:

*Plus* - The flame detection system works with clean code, very optimised and simple to follow.
       - The flame detection system outputs on multiple LEDs allowing me to see whether their is a flame or not.

*Minus* - The flame detections system output is kind of pointless, only alerting via light, which kind of defeats the purpose when you can see the flame.

*Implication* - The system allows the user to detect whether there is a flame within the vicinity. I would suggest adding a buzzer to improve on.

**Evaluator 3: Max E**:

Plus - Meets functional requirements quite well. The code is short and well-written to ensure maximum efficiency. Module works well and system runs accordingly with no fault.

Minus - There could be more done with this mode instead of just a few LEDs and flame sensor. There could be more test cases to work with.

Implication - Maybe include something with another sensor, such as a buzzer in case the flame stays for too long or a button to revert the system back in case of failure. Something else to enhance this working module and linking to a more real-world issue. Aside from that, the code is excellent and the module works well with its requirements.

### Project Evaluation

### Functional success criteria

The system successfully detected a flame using the digital flame sensor. When a flame was detected, it displayed a warning message and turned the onboard LED on. When no flame was present, it displayed a safe status and turned the LED off.

### Non-functional success criteria

The system was reliable, easy to use, and responded quickly. Checking the sensor every 0.5 seconds provided a consistent response without noticeable delays.

### Performance

During testing, the sensor was accurately able switched between safe and warning states. The program ran continuously without crashing and produced consistent results.

### Improvements

* Software: Add a buzzer to provide an audible warning when a flame is detected.



