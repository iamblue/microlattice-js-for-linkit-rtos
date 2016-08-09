# FOTA


| API | description |
| --- | --- |
| __fota | Help you to starting fota. |

# Native binding API 


### __fota

* Content

``` js
  __fota(
    cdn url, // string
  )

```

* Example

``` js

  __wifi({
    mode: 'station', // default is station
    auth: 'PSK_WPA2',
    ssid: 'Input your ssid',
    password: 'Input your password',
  });

  global.eventStatus.on('wifiConnect', function() {
  __fota("http://cdn.mediatek.com/firmwares/PuxQFhlHKM2B/36c8248e37161cc333a6cbb6f2586a42/output.bin");
  });
```