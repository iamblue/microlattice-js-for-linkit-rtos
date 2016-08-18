# Wifi


| API | description |
| --- | --- |
| __wifi | Help you to set wifi mode. |

## Required

* ml-event

## Native binding API 

### AP mode

``` js
__wifi({
  mode: 'ap', // default is station
  auth: 'PSK_WPA2',
  ssid: 'Input your ssid',
  password: 'Input your password',
});

```

### Station mode

``` js

__wifi({
  mode: 'station', // default is station
  auth: 'PSK_WPA2',
  ssid: 'Input your ssid',
  password: 'Input your password',
});

global.eventStatus.on('wifiConnect', function(){
  // if wifi connect ...
});

```
