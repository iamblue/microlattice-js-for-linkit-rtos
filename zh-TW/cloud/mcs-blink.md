# 如何透過 MCS switch 頻道點燈


* 首先請至 MCS create 好一個內有 switch datachannel 且新的 test device.
* 請參考這個 [創建好 ml 專案] (https://iamblue.gitbooks.io/microlattice-js-for-linkit-rtos/content/zh-TW/intro/create.html)
* 範例程式碼：

``` js
__pinmux(35, 8);

var status = 0;

__wifi({
  mode: 'station', // default is station
  auth: 'PSK_WPA2',
  ssid: 'Input your ssid',
  password: 'Input your password',
});

global.eventStatus.on('wifiConnect', function() {
  // if wifi connect ...
  __mqttClient(
    "mqtt.mcs.mediatek.io",                 // string
    "1883",                                 // string
    "mcs/{your deviceId}/{your deviceKey}/{your dataChannel}", // string
    'mcs-client',                               // string
    0,                  // number: Qo0: 0, Qo1: 1, Qo2: 2
    function(data) {
      if (data.indexOf("switch,1") === 14) {
        __gpioWrite(35, 1);
      } else if (data.indexOf("switch,0") === 14) {
        __gpioWrite(35, 0);
      }
      print(data);
  });
});

```