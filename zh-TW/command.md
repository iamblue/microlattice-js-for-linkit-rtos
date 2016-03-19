# 如何透過 MCS switch 頻道點燈




``` js
var EventEmitter = require('ml-event').EventEmitter;
var eventStatus = new EventEmitter();
global.eventStatus = eventStatus;

/* mcs config */
var deviceId = 'Input your deviceId';
var deviceKey = 'Input your deviceKey';
var heartBeatCommand = deviceId + ',' + deviceKey + ',0';

/* Setting wifi config */
wifi({
  mode: 'station', // default is station
  auth: 'PSK_WPA2',
  ssid: 'Input your wifi ssid',
  password: 'Input your wifi password',
});
var firstConnect = 0;

/* Setting gpio pinmux */
pinmux(35, 8);

/* Listening wifi connected event */
global.eventStatus.on('wifiConnect', function(data){
  tcpClient('52.77.236.179', 443, function(data) {
    if (firstConnect === 0) {
      tcpSend(heartBeatCommand);
    }
    if (data.indexOf('switch,1') === 40) {
      gpioWrite(35, 1);
    } else {
      gpioWrite(35,0);
    }
  });
});

```