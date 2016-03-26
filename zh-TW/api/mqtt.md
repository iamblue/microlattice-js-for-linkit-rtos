# MQTT


| API | description |
| --- | --- |
| __mqttClient | Help you to connect MQTT server. |
| __mqttServer | Help you to build MQTT server. |

# Native binding API


### __mqttClient
* Content

``` js
__mqtt(
  host,                 // string
  port,                 // string
  topic,                // string
  clientId,             // string
  qos,                  // number: Qo0: 0, Qo1: 1, Qo2: 2
  recieve msg callback, // function
)

```

### mqttServer
