# MQTT


| API | description |
| --- | --- |
| __mqttClient | Help you to connect MQTT server. |
| __mqttSend | Help you to send MQTT message. |
| __mqttClose | Help you to turn off MQTT. |


# Native binding API


### __mqttClient
* Content

``` js
__mqttClient(
  host,                 // string
  port,                 // string
  topic,                // string
  clientId,             // string
  qos,                  // number: Qo0: 0, Qo1: 1, Qo2: 2
  recieve msg callback, // function
)

```

### __mqttSend (TBD)
### __mqttClose (TBD)

