# MQTT
---
## Broker

An underlying MQTT Broker is responsible for controlling MQTT communication. This will typically be part of your [Rook Daemon](https://github.com/RoboticsOrchestrationKit/rook-daemon-java) deployment, but it is possible to simply run any broker you choose instead.

## Inputs

All inputs should be published using the following MQTT topic pattern:
```
rook/io/i/{device_name}/{data_type}
```

## Outputs

All outputs should be published using the following MQTT topic pattern:
```
rook/io/o/{device_name}/{data_type}
```

