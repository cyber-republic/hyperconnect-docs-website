# Internet-of-Things Concepts

### Edge Client
The Edge Client is the software component that runs on the IoT device and can be used with a Graphical User Interface (GUI) or via Command Line (Terminal).

### Remote Controller
The Remote Controller is the software component that runs on the mobile phone or computer of a user and allows the monitoring and remote control of the connected edge clients via a graphical user interface.

### Devices
Devices are the hardware to which the sensors are connected. By running IoT relevant software on the devices , such as the Edge Client, devices also serve as the gateway to remote systems and allow the exchange of data.

### Sensors
Sensors allow the measurement of physical properties and translate these into electric signals that can then be processed by a device.

### Sensor Groups
Sensor Groups allow the flexible collection of sensors by their parameters, locations, properties for simple management by the user. For example, a SenseHat Board for the Raspberry Pi has multiple sensors that are all located on a single board. These sensors (sensor attributes) may all be grouped together.

### Sensor Attributes
Each sensor can only measure one certain physical property, therefore to each sensor, one attribute may be defined.

### Sensor Scripts
Bare hardware sensors, require special programs (scripts) to translate the electrical impulses into meaningful data. To each sensor, a sensor script may be defined.

### Rules
Rules are the user defined custom logic that defines how and when the system should react changes in the environment, based on the collected data. Data is constantly analyzed by the rules engine to check if any of the rules have been fulfilled.

### Actions
Actions are the responses to changes in the environment, predefined by rules.
The fulfilment of a rule and an action are considered an event.

### Events
Events are considered the process of fulfilment of certain predefined rules. If a rule with a certain logic is fulfilled, an action is carried out automatically by the rules engine.
For example, by predefining a rule such as that if the measured temperature by the sensor 'temp' reaches 30 degrees Celsius, turn on the LED light. An event is considered the fulfilment of the rule 'above 30 degrees' and the action to turn on the LED light.
