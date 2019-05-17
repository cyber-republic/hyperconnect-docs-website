# Generated random values on Windows and Local Events

In this tutorial an Input Sensor Attribute will be created, which instead of reading from an actual Sensor, will generate its own random value between 0 and 9.

The Output Sensor Attribute will have the purpose of writing a value into a local .txt file. These values provided to the Output Sensor Attribute will be by rules that are defined in so called 'Events'.

The following situation should be handled:

- If the value from the Input Attribute is above 5, set the Output Attribute to 'True'. (It will write the value 'True' into the .txt file)

- If the value from the Input Attribute is below 5, set the Output Attribute to 'False'. (It will write the value 'True' into the .txt file)

Great, let's get started!


#### Open the 'Sensors' view.

![Screenshot](images/generated-numbers-temperature-tutorial-1.png)

#### Add a new Sensor with the name 'RandomValue' and Type 'Random' or similar.

![Screenshot](images/generated-numbers-temperature-tutorial-2.png)

#### Click 'Add' to save the new Sensor Group.

![Screenshot](images/generated-numbers-temperature-tutorial-3.png)

#### Click 'Configure'.

![Screenshot](images/generated-numbers-temperature-tutorial-4.png)

#### No attributes have been configured yet.

![Screenshot](images/generated-numbers-temperature-tutorial-5.png)

#### Create a new Attribute. Fill in the values:
- Name: rand
- Type: integer
- Direction: input (from sensor to device)
- Interval: 5 sec

![Screenshot](images/generated-numbers-temperature-tutorial-6.png)

#### The attribute has been created successfully.

![Screenshot](images/generated-numbers-temperature-tutorial-7.png)


#### Click the '< >' button to configure the Sensor Attribute Script.

![Screenshot](images/generated-numbers-temperature-tutorial-8.png)


#### To start editing, click the 'Edit' button.

![Screenshot](images/generated-numbers-temperature-tutorial-9.png)


#### Edit mode will appear and the script may be added manually or from a template.

![Screenshot](images/generated-numbers-temperature-tutorial-10.png)


#### Select the template 'randomGenerator (Test)'.

![Screenshot](images/generated-numbers-temperature-tutorial-11.png)


#### The script will be added to the script body.

![Screenshot](images/generated-numbers-temperature-tutorial-12.png)


#### Click 'Validate' to validate the script.

![Screenshot](images/generated-numbers-temperature-tutorial-13.png)


####  After successful validation, click 'Save' to save the changes. Then click 'Back to Attribute List'.

![Screenshot](images/generated-numbers-temperature-tutorial-14.png)


#### In the overview, the Script State will now show as 'valid'.

![Screenshot](images/generated-numbers-temperature-tutorial-15.png)


#### Toggle the button in the Action area to activate the Sensor Attribute.
#### The collection of data will start at this point.

![Screenshot](images/generated-numbers-temperature-tutorial-16.png)


#### The Attribute State has now changed to active.

![Screenshot](images/generated-numbers-temperature-tutorial-17.png)


#### In the 'Add Attribute' section, create a new Attribute with the following details:
- Name: resultToText
- Type: boolean
- Direction: output (from device to sensor)
- Interval: Event-driven (cannot be changed for output direction)

![Screenshot](images/generated-numbers-temperature-tutorial-18.png)


#### Click the 'Add' to save the new attribute.

![Screenshot](images/generated-numbers-temperature-tutorial-19.png)


#### In the overview, click the '< >'(Script) button.

![Screenshot](images/generated-numbers-temperature-tutorial-20.png)


#### In the bottom left corner, click 'Edit' to enable editing of the script.

![Screenshot](images/generated-numbers-temperature-tutorial-21.png)


#### The script can now be edited, as the 'Validate' button has appeared.

![Screenshot](images/generated-numbers-temperature-tutorial-22.png)


#### Enter the following detail:

- Input Parameter: True

#### From the 'Templates' dropdown in the top-right corner, select the 'writeToFile (Test)' template.

![Screenshot](images/generated-numbers-temperature-tutorial-23.png)


#### Click the 'Validate' button.

![Screenshot](images/generated-numbers-temperature-tutorial-24.png)


#### Save the changes by clicking the 'Save' button and then click 'Back to Attribute List' to return to the overview.

![Screenshot](images/generated-numbers-temperature-tutorial-25.png)


#### The script state for the attribute 'resultToText' is now valid.

![Screenshot](images/generated-numbers-temperature-tutorial-26.png)


#### Click on the switch to activate the 'resultToText' attribute.

![Screenshot](images/generated-numbers-temperature-tutorial-27.png)


#### Great, both Attributes are now valid and active!

![Screenshot](images/generated-numbers-temperature-tutorial-28.png)


#### In the Menu, click 'Events'.
#### Then, click the 'Add Events' button.

![Screenshot](images/generated-numbers-temperature-tutorial-29.png)


#### For this scenario, we will need to eventually create two events. The first Event will handle the situation if the random generated number by the input Attribute is above 5, then save the value 'true' to the test.txt file.

![Screenshot](images/generated-numbers-temperature-tutorial-30.png)


#### Let's fill out the details for the first event scenario as follows:

##### Event Source
- Sensor: RandomValue (Random)
- Attribute: rand (integer)
- Attribute Average: Real-Time
- Event Condition: greater than
- Event Value: 5

##### Event Action
- Sensor: RandomValue (Random)
- Attribute: resultToText
- Event Trigger Value: True

##### Event Parameters
- Name: greaterThan5

#### Finally, click the 'Add' button to save the event.

![Screenshot](images/generated-numbers-temperature-tutorial-31.png)


#### In the Event List overview, click 'Add Event' to create the second event.

![Screenshot](images/generated-numbers-temperature-tutorial-32.png)


#### This second will handle the situation if the random generated number by the input Attribute is below 5, then save the value 'false' to the test.txt file.

![Screenshot](images/generated-numbers-temperature-tutorial-33.png)


#### Let's fill out the details for the first event scenario as follows:

##### Event Source
- Sensor: RandomValue (Random)
- Attribute: rand (integer)
- Attribute Average: Real-Time
- Event Condition: less than
- Event Value: 5

##### Event Action
- Sensor: RandomValue (Random)
- Attribute: resultToText
- Event Trigger Value: False

##### Event Parameters
- Name: lessThan5

![Screenshot](images/generated-numbers-temperature-tutorial-34.png)


#### Finally, click the 'Add' button to save the event.

![Screenshot](images/generated-numbers-temperature-tutorial-35.png)


#### Both Events are now created and will be listed in the overview.
#### Activate both Events by clicking on the switches.

![Screenshot](images/generated-numbers-temperature-tutorial-36.png)


#### Now that the Events are active, the Edge Client will start writing the results of the evaluations from the Input Attribute to the Output Attribute. In this case, if the value from the input attribute is greater than 5, write the value 'True' in the test.txt file, if it is below 5, overwrite the value with the value 'False'.

![Screenshot](images/generated-numbers-temperature-tutorial-37.png)


#### Let us check the current value of the Input Attribute.
#### Click 'Sensors' in the Menu, then for the input Attribute, click the 'Overview' button. The Input Attribute will be shown with its latest value.
#### Use the refresh button in the top-right corner to check the latest value.
#### Remember, the value is always updated after every 5 seconds.

![Screenshot](images/generated-numbers-temperature-tutorial-38.png)


#### In File Explorer on Windows, navigate to the folder with the downloaded files for HyperConnect and locate the 'test.txt' file.
#### Open 'test.txt' in Notepad or similar program.

![Screenshot](images/generated-numbers-temperature-tutorial-39.png)


#### Because the read value was 2, which is less than 5, the second event was fulfilled successfully and the value 'false' was written in the test.txt file.

![Screenshot](images/generated-numbers-temperature-tutorial-40.png)


#### Back to the overview, click the 'Refresh' button in the top-right corner to see the new value read from the input attribute.
#### The value was 6, so the first event must have been fulfilled.

![Screenshot](images/generated-numbers-temperature-tutorial-41.png)


#### Correctly, if you re-open the test.txt file, the value was set to 'true'.

![Screenshot](images/generated-numbers-temperature-tutorial-42.png)

#### Awesome, you did it! This is a good example of how data input streams can be monitored automatically and that the rules can be predefined for any outcome.


#### Did you notice the that Input Attribute when it was exactly 5 was not handled in this tutorial?  
#### Give it a try and create a third event which sets the boolean value 'true' when the Input Attribute is 'equal to' 5.
Note: 'greater than or equal' and 'less than or equal' options are not available by default to avoid any overlapping in the Rules Engine.
#### Good luck and feel free to ask in the Forum if you face any issues!
