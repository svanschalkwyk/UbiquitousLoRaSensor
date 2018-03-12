Manifesto for a Universal Wireless Sensor Network
=

## Wireless sensor networks will not talk to each other
If we are to have a vast network of wireless sensors, we need to get sensor manufacturers to create sensor boards. Manufacturers are encouraged to copy and add enhancements to this platform, and still produce networks using their own, proprietary, protocols.

What we would like to do in this project, is to formulate a protocol and open source hardware for a ubiquitous wireless sensor network. We are proposing a protocol which may be employed by LoRaWan, LoRa, WiFi and any other network. Gateways will enable communication between networks, but the sensor data protocol will be universal.

## Measurement Units
One of the main issues standing in the way of a universal sensor network, is the non-universality of measurement units. This has impacted even projects such as the Hubble Telescope. Conversion is sometimes fraught with mistakes.

We propose to use the Unified Code for Units of Measure (http://www.unitsofmeasure.org) as a starting (and possible, an end point, as it is very comprehensive). You are encouraged to read this specification, as it gives a wonderful perspective on measurement, starting from earliest history.
This specification also allows for *new measurement terms* to be created using the BNF specification in the diagram below:
[
](./images/bnf_syntax.jpg)

## Common sensor measurement units
For the sake of brevity, we list only the units we believe to be the most commonly used. Readers are encouraged to read the addenda to the specification, particularly C.3  ALPHABETIC INDEX BY KIND OF QUANTITY

### Temperature, Pressure, Humidity
|name|kind of quantity|c/s|c/i|extension
|--|--|--|--|--
|kelvin|temperature|K|K|
|Celsius|temperature|Cel|CEL
|Fahrenheit|temperature|[degF]|[DEGF]
|pascal|pressure|Pa|PAL
|relative humidity|humidity|%RH|%RH
|absolute humidity|humidity|AHD|AHD|g/m3
|volt|electric potential|V|V
|millivolt|electric potential|mV|mV
|microvolt|electric potential|uV|uV
|ohm|electric resistance|Ohm|OHM
|siemens|electric conductance|

where c/s = case-sensitive, c/i == case-insensitive











https://www.eclipse.org/uomo/
http://www.unitsofmeasure.org/trac
https://jcp.org/en/jsr/detail?id=256


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk1MTUwNjUyN119
-->