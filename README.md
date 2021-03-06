# Manifesto for a Universal Wireless Sensor Network


## Wireless sensor networks will not talk to each other
If we are to have a vast network of wireless sensors, we need to convince sensor manufacturers to create sensor modules. Manufacturers are encouraged to copy and add enhancements to this platform, and still produce networks using their own, proprietary, protocols.

What we would like to do in this project, is to formulate a protocol and open source hardware for a ubiquitous wireless sensor network. We are proposing a protocol which may be employed by LoRaWan, LoRa, WiFi and any other network. Gateways will enable communication between networks, but the sensor data protocol will be universal.

## Measurement Units
One of the main issues standing in the way of a universal sensor network, is the non-universality of measurement units. This has impacted even projects such as the Hubble Telescope. Unit conversion is sometimes fraught with mistakes.

We propose to use the Unified Code for Units of Measure, found here http://www.unitsofmeasure.org, as a starting (and possible, an end point, as it is very comprehensive). You are encouraged to read this specification, as it gives a wonderful perspective on measurement, starting from earliest history.
This specification also allows for *new measurement units* to be created using the BNF specification in the diagram below:
![BNF Syntax to use for new units](https://github.com/svanschalkwyk/UbiquitousLoRaSensor/blob/master/images/bnf_syntax.jpg)

## Common sensor measurement units
For the sake of brevity, we list only the units we believe to be the most commonly used. Readers are encouraged to read the addenda to the specification, particularly the section C.3  ALPHABETIC INDEX BY KIND OF QUANTITY

### Temperature, Pressure, Humidity
|name|kind of quantity|c/s|c/i|definition
|--|--|--|--|--
|kelvin|temperature|K|K|
|Celsius|temperature|Cel|CEL
|Fahrenheit|temperature|[degF]|[DEGF]
|pascal|pressure|Pa|PAL
|relative humidity|humidity|%RH|%RH
|absolute humidity|humidity|AHD|AHD|g/m3
|ampere|electric current|A|A|C/s
|volt|electric potential|V|V
|millivolt|electric potential|mV|mV
|microvolt|electric potential|uV|uV
|ohm|electric resistance|Ohm|OHM|V/A
|weber|magnetic flux|Wb|WB|V.s
|siemens|electric conductance|S|SIE|Ohm-1
|tesla|magnetic flux density|T|T|Wb/m2
|henry|inductance|H|H|Wb/A
|lumen|luminous flux|lm|LM|cd.sr
|lux|illuminance|lx|LX|lm/m2
|second|time|s|S
|minute|time|min|MIN|60s
|hour|time|h|HR|60min
|day|time|d|DAY|24h
where c/s = case-sensitive, c/i = case-insensitive

### Usage
The usage section will be expanded and changed as more collaborators join the project. If you have input, suggestions, or just want to join for updates, please contact us at  [join us](mailto:steph@remcam.net). 

## Protocols
1. MQTT (The Things Network https://www.thethingsnetwork.org/)
2. 
3. Us....
#### 1. MQTT

#### 2. ......

#### 3. Proposed Sensor Data Packaging
To conserve as much battery power as possible, data packages have to be as small as reasonably possible. In order to make data packages ubiquitous and human-readable, we propose an ASCII data format as well as a binary format. We respectfully request community input on this. 
##### ASCII 
We propose a data package consisting of:

|datetime|number of bytes in read|reading|units|
|--|--|--|--|
|ISO 8601:2000 YYMMDDTHHMMSSZZZZZ|bytes in data|ASCII|as above
|181231T235959-0200|


It is entirely reasonable to present time as a binary number, and/or an offset, but in the interest of readability we propose using YYMMDDTHHMMSSZZZZZ. We propose to use UTC for all sensor packages, and we request community input regarding this. 

A sample sensor reading looks like this after formatting:

|datetime|number of data bytes|reading|units
|---|---|---|---
|180312T230530-0600|5| -12.0 | CEL
|alternatively: |
|180312230530 (all readings in UTC)

#### Multiple readings in a data packet
In the case of modules containing multiple sensors, and where the datetime information is shared, we propose the following:

|datetime|number of bytes in read| number of reading packages to follow|unit|termination
|---|---|---|---|---
|180312T230530-0600|0| 3| PKG | linefeed (\n)
||5| -10.0 | CEL | \n
||4| 22.5 | %RH | \n
||6| -12.46 | V | \n

##### Binary
To follow.


#### References:
https://www.eclipse.org/uomo/
http://www.unitsofmeasure.org/trac
https://jcp.org/en/jsr/detail?id=256
#### Interesting Reading:
[Toward a Robust Sparse Data Representation for Wireless Sensor Networks](https://arxiv.org/pdf/1508.00230.pdf)


<!--stackedit_data:
eyJoaXN0b3J5IjpbMjEyNDYwNzY5NV19
-->
