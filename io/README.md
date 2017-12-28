# Rook IO
---
## Description
Rook IO aims to improve compatibility of simple input and output control through common usage patterns, while supporting interoperability of multiple middlewares through the [Rook Daemon](https://github.com/RoboticsOrchestrationKit/rook-daemon-java).

## Devices
A "device" represents a single input or output. For instance, an ultrasonic sensor and a servo would each be considered a separate device.

### Device Name
Every device has a unique name. Names must be UTF-8 encoded, and can only contain the following characters: A-Z, a-z, 0-9, -, _, and space. Keep in mind that the device name will be sent in all messages, so keeping it short will keep your messages small.

### Device Data Type
All IO values are represented as a blob/byte-array/opaque-bytes. In order to provide context into how to interpret this data, a data-type is assigned to a device. When endianness is required, all values are represented as little-endian. Currently, valid data types are:
* BLOB - An opaque array of bytes
* UTF8 - A UTF-8 encoded string
* U8 - unsigned 8-bit value
* U16 - unsigned 16-bit value (little-endian)
* U32 - unsigned 32-bit value (little-endian)
* U64 - unsigned 64-bit value (little-endian)
* I8 - signed 8-bit value (two's compliment)
* I16 - signed 16-bit value (little-endian, two's compliment)
* I32 - signed 32-bit value (little-endian, two's compliment)
* I64 - signed 64-bit value (little-endian, two's compliment)


## Middlewares
* [MQTT](./mqtt/)
* [Web Socket](./websocket/)


## Libraries
* [rook-client-java](https://github.com/RoboticsOrchestrationKit/rook-client-java)

