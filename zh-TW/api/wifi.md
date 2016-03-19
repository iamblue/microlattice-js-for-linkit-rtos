# Wifi


| API | description |
| --- | --- |
| wifi | Help you to set wifi mode. |

## Required

* ml-event

## API 

### AP mode

``` js
wifi({
  mode: 'ap', // default is station
  auth: 'PSK_WPA2',
  ssid: 'Input your ssid',
  password: 'Input your password',
});

```

### Station mode

``` js
var EventEmitter = require('ml-event').EventEmitter;
var eventStatus = new EventEmitter();
global.eventStatus = eventStatus;

wifi({
  mode: 'station', // default is station
  auth: 'PSK_WPA2',
  ssid: 'Input your ssid',
  password: 'Input your password',
});

global.eventStatus.on('wifiConnect', function(){
  // if wifi connect ...
});

```


