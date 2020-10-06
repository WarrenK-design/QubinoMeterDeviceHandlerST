# Qubino Device Handler 
This repostory holds the device handler of the [Qubino Energy Meter](https://qubino.com/manuals/Smart_Meter.pdf). The default device handler which is used for the Qubino Meter is the [Aeon Home Energy Meter](https://github.com/SmartThingsCommunity/SmartThingsPublic/blob/master/devicetypes/smartthings/aeon-home-energy-meter.src/aeon-home-energy-meter.groovy) however this device handler does not currently support the full range of meter readings the Qubino Energy Meter supports. 

This device handler uses the Z-Wave Meter Command class version 3 to support readings of:
1. Power - Watts(W)
2. Voltage - Volts(V)
3. Energy - Kilo Watt Hours(kWh)
4. Current - Amps(A)
5. Power Factor - Unitless
6. Apparent Energy - Kilo Volt Ampere Hours(kVAh)

Through the REST API values of Voltage, Power and Energy can be accessed through the capabilities of the *Energy Meter*, *Power Meter* and *Voltage Measurement*. Custom capabilities still must be addded to gain access to all readings through the API. 

## Testing 
If you wantto poll the meter to see if it is recording measuremnts send a refresh command to the meter through the [Classic SmartThings app](https://play.google.com/store/apps/details?id=com.smartthings.android&hl=en&gl=US), thhe simulator in the [SmartThings IDE](https://graph.api.smartthings.com/) or through the REST API executing a [*refresh*](https://smartthings.developer.samsung.com/docs/api-ref/st-api.html#operation/executeDeviceCommands) command. 

A sample output from the logs after executing a *refresh* command is shown below. 