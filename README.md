# SeatalkConverter
Arduino sketch that converts Seatalk to NMEA, giving raw $STALK messages on USB

## Introduction
Raymarine Seatalk is using a single line read/write bus that uses 9-bit serial protocol to transfer its proprietary messages. This project creates a hardware bridge between a Seatalk network and a NMEA network by extracting the Seatalk messages from the one-line bus and sending it in NMEA format on the USB port

## Dependencies
https://github.com/manuel-rabade/Alt9SoftSerial

## Instructions
### Sketch
Compile and upload sketch to any Arduino supported by the Alt9SoftSerial library. 

### Hardware
Create a simple voltage divider using two resistors to make a 5 volt signal from the 12 volt Seatalk signal and connect it to the read pin defined by Alt9SoftSerial. Connect ground between the Seatalk network and either power it from the same using the built in power converter or let the Arduino be powered from USB.

### Expected result
Monitor the output from the Arduino console while the Seatalk network is up and instruments running, it will start printing $STALK NMEA messages over USB containing everything sent over the Seatalk network.

## Links
http://www.thomasknauf.de/seatalk.htm
This is a great source of information, containg unidirectional and bidirectional hardware interfaces more complicated (and probably safer) than my suggested voltage divider. It also covers in depth description of the Seatalk protocol and its messages
