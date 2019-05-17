# Raspberry Pi + SenseHat Temperature Sensor + LED Matrix with Local Events

In this tutorial an Input Sensor Attribute will be created, which will measure the actual temperature with a sensor on the Raspberry Pi SensHat

The Output Sensor Attribute will have the purpose of showing the letter 'H' for Hot and 'C' for Cold on the LED Matrix on the SenseHat.

The following situation should be handled:

- If the value from the Input Attribute is above a certain temperature, set the Output Attribute to 'H'.

- If the value from the Input Attribute is below a certain temperature, set the Output Attribute to 'C'.

Great, let's get started!

#### Open the 'Sensors' view.

![Screenshot](images/sensehat-temperature-local-event-tutorial-1.png)

#### Enter the name 'Raspi' and type 'Raspberry Pi'. Click 'Add' to create the new Sensor Group.

![Screenshot](images/sensehat-temperature-local-event-tutorial-2.png)

#### The new Sensor Group 'Raspi' is added to the Sensor List. Click 'Configure' to add new Sensor Attributes.

![Screenshot](images/sensehat-temperature-local-event-tutorial-3.png)

#### By clicking 'Configure', the List of defined attributes appears as well as the 'Add Attribute' section.

![Screenshot](images/sensehat-temperature-local-event-tutorial-4.png)

#### Create a new attribute:
- Name: temp
- Type: double
- Direction: Input (from sensor to device)
- Interval: 5 sec

![Screenshot](images/sensehat-temperature-local-event-tutorial-5.png)

#### Click 'Add' to save the new attribute.

![Screenshot](images/sensehat-temperature-local-event-tutorial-6.png)

#### In the Sensor Attribute List, click the '< >'(Script) button.

![Screenshot](images/sensehat-temperature-local-event-tutorial-7.png)

#### Click the 'Edit' button to enable editing.

![Screenshot](images/sensehat-temperature-local-event-tutorial-8.png)

#### Add the following script:
```
from sense_hat import SenseHat

sense = SenseHat()
sense.clear()

temp = sense.get_temperature()
print(temp)
```

![Screenshot](images/sensehat-temperature-local-event-tutorial-9.png)

#### Click 'Validate'. The Python compiler will check if everything is correct.

![Screenshot](images/sensehat-temperature-local-event-tutorial-10.png)

#### Click 'Save'. Then click 'Back to Attribute List'.

![Screenshot](images/sensehat-temperature-local-event-tutorial-11.png)

#### After click 'Back to Attribute List', the overview list will be shown.

![Screenshot](images/sensehat-temperature-local-event-tutorial-12.png)

#### In the 'Add Attribute' section on top, add a new Attribute:
- Name: led
- Type: string
- Direction: output(device to sensor)
- Interval: Event-driven

#### Click 'Add'.

![Screenshot](images/sensehat-temperature-local-event-tutorial-13.png)

#### The 'led' attribute has been added successfully.
#### Click the '< >'(Script) button of the 'led' attribute.

![Screenshot](images/sensehat-temperature-local-event-tutorial-14.png)

#### Click 'Edit' to enable editing.

![Screenshot](images/sensehat-temperature-local-event-tutorial-15.png)

#### Editing has been enabled if the 'Validate' button is visible.

![Screenshot](images/sensehat-temperature-local-event-tutorial-16.png)

#### Add the following script to the body:
```
import sys
parameter=sys.argv[1]

from sense_hat import SenseHat

sense=SenseHat()
sense.show_letter(parameter, text_colour=[255,0,0])

print("DONE")
```
#### Enter the Input Parameter: H

![Screenshot](images/sensehat-temperature-local-event-tutorial-17.png)

#### Click 'Validate'.
#### On the Raspberry Pi SenseHAT, the letter H will be shown on the LED matrix. This is for validation only.

![Screenshot](images/sensehat-temperature-local-event-tutorial-18.png)

#### Save the changes and return to the Attribute List.

![Screenshot](images/sensehat-temperature-local-event-tutorial-19.png)

#### Activate both Attributes by clicking the switch in their rows.

![Screenshot](images/sensehat-temperature-local-event-tutorial-20.png)

#### Let's check the read values of the input attribute.
#### Click 'Sensors' in the menu.

![Screenshot](images/sensehat-temperature-local-event-tutorial-21.png)

#### Click the 'Overview' button.

![Screenshot](images/sensehat-temperature-local-event-tutorial-22.png)

#### The Latest Value read was around 35.77 .

![Screenshot](images/sensehat-temperature-local-event-tutorial-23.png)

#### Click the 'Refresh' in the top right corner. The Latest Value read was around 35.74 . We will use this data to configure our events.

![Screenshot](images/sensehat-temperature-local-event-tutorial-24.png)

#### In the Menu, click 'Events'. Then click 'Add Event'.

![Screenshot](images/sensehat-temperature-local-event-tutorial-25.png)

#### Events consist of an Event Source and an Event Action.
- Event Sources are the values from Input Attributes.
- Event Actions are commands sent to the Output Attributes.

![Screenshot](images/sensehat-temperature-local-event-tutorial-26.png)

#### Select the following values:

##### Event Source
- Sensor: Raspi (Raspberry Pi)
- Attribute: temp (double)
- Attribute Average: Real-Time
- Event Condition: greater than
- Event Value: 37.5 (or similar, depending on the average temp on your device)

##### Event Action
- Sensor: Raspi (Raspberry Pi)
- Attribute: led (string)
- Trigger Value: H (for Hot)

##### Event Name
- Name: TempHot (or anything memorable)

#### Click 'Add' to save and return to overview.

![Screenshot](images/sensehat-temperature-local-event-tutorial-27.png)

#### In the overview section, let's add a second event, in case the temp goes below 37.5 , how should the output value be set.

#### Click 'Add Event'.

![Screenshot](images/sensehat-temperature-local-event-tutorial-28.png)

#### Let's configure the new event.

![Screenshot](images/sensehat-temperature-local-event-tutorial-29.png)

#### Select the following values:

##### Event Source
- Sensor: Raspi (Raspberry Pi)
- Attribute: temp (double)
- Attribute Average: Real-Time
- Event Condition: less than
- Event Value: 37.5 (or similar, depending on the average temp on your device)

##### Event Action
- Sensor: Raspi (Raspberry Pi)
- Attribute: led (string)
- Trigger Value: C (for Cold)

##### Event Name
- Name: TempCold (or anything memorable)

#### Click 'Add' to save the new event and return to the overview.

![Screenshot](images/sensehat-temperature-local-event-tutorial-30.png)

#### Great!

![Screenshot](images/sensehat-temperature-local-event-tutorial-31.png)

#### Let's activate both events by clicking the switches.

![Screenshot](images/sensehat-temperature-local-event-tutorial-32.png)

#### In case the temperature is above the defined 37.5 degrees, the Raspberry Pi will display the letter 'H'.

![Screenshot](images/sensehat-temperature-local-event-tutorial-33.jpg)

#### By blowing over the temperature sensor and lowering the temperature of the board, the Raspberry Pi will monitor the changes and will change the letter 'H' to the letter 'C'.

![Screenshot](images/sensehat-temperature-local-event-tutorial-34.jpg)

#### Excellent! Please feel free to post in the [Forum](https://forum.cyberrepublic.org/c/hyperconnect) if you have any questions or face any issues.
