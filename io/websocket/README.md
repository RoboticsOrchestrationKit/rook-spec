# Web Sockets
---
## Server
A web server will need to control communication between all Web Socket Clients. This is similar to how an MQTT broker would facilitate communication between multiple MQTT Clients. This will typically be part of your [Rook Daemon](https://github.com/RoboticsOrchestrationKit/rook-daemon-java) deployment, which will also facilitate communication between both MQTT and Web Socket Clients.

## Connection
Each client communicates with the web server using a configured Web Socket URL, and by specifying "rook_io" as the underlying Web Socket Sub-Protocol.

## Inputs

### Subscribe: All Inputs
To subscribe to all inputs, a client sends the following message:
```
{"type": "input_subscribe"}
```

### Subscribe: Specific Input
To subscribe to a specific input, a client sends the following message:
```
{"type": "input_subscribe", "name": "<the_input_name>"}
```

### Unsubscribe: All Inputs
To unsubscribe from an "all inputs subscription", a client sends the following message:
```
{"type": "input_unsubscribe"}
```

### Unsubscribe: Specific Input
To unsubscribe from a specific input, a client sends the following message:
```
{"type": "input_unsubscribe", "name": "<the_input_name>"}
```

### Dispatch Input Value
To dispatch an underlying input value for all clients, a client sends the following message:
```
{"type": "input_publish", "name": "<the_input_name>", "dataType": "<the_data_type>", "value": "<base64_encoded_bytes>"}
```

### Receive Input Updates
When an input is updated, the server will asynchronously dispatch the following message to all subscribed clients:
```
{"type": "input", "name": "<the_input_name>", "dataType": "<the_data_type>", "value": "<base64_encoded_bytes>"}
```


## Outputs

### Subscribe: All Outputs
To subscribe to all outputs, a client sends the following message:
```
{"type": "output_subscribe"}
```

### Subscribe: Specific Outputs
To subscribe to a specific output, a client sends the following message:
```
{"type": "output_subscribe", "name": "<the_output_name>"}
```

### Unsubscribe: All Outputs
To unsubscribe from an "all outputs subscription", a client sends the following message:
```
{"type": "output_unsubscribe"}
```

### Unsubscribe: Specific Output
To unsubscribe from a specific output, a client sends the following message:
```
{"type": "output_unsubscribe", "name": "<the_output_name>"}
```

### Dispatch Output Value
To dispatch an underlying output value for all client, a client sends the following message:
```
{"type": "output_publish", "name": "<the_output_name>", "dataType": "<the_data_type>", "value": "<base64_encoded_bytes>"}
```

### Receive Output Updates
When an output is updated, the server will asynchronously dispatch the following message to all subscribed clients:
```
{"type": "output", "name": "<the_output_name>", "dataType": "<the_data_type>", "value": "<base64_encoded_bytes>"}
```

