# 如何透過 MCS 使用 PWM 頻道點燈(漸進式)

* 首先請至 MCS 創建好一個內有 led (PWM control datachannel) 的 test device.
* 請參考這個 [創建好 ml 專案](https://iamblue.gitbooks.io/microlattice-js-for-linkit-rtos/content/zh-TW/intro/create.html)
* 到您創建好的 ml 專案根目錄下: `npm install ml-pwm --save`
* 至 featureConfig.json 添加: `ml-pwm: true`
* 範例程式碼：

``` js
  __pinmux(31, 9);  // set pinmux
  __pwmRegister(32, 4, 400000);  // registe pwm

  __wifi({
    mode: 'station', // default is station
    auth: 'PSK_WPA2',
    ssid: 'Input your ssid',
    password: 'Input your password',
  });

  global.eventStatus.on('wifiConnect', function() {
    __mcs(
      "mqtt.mcs.mediatek.com",                  // string
      "1883",                                   // string
      "mcs/{your deviceId}/{your deviceKey}/+", // string
      '7687client',                             // string
      0,                  // number: Qo0: 0, Qo1: 1, Qo2: 2
      function(data) {
        print(data);
        if (data.split(',')[1] === 'led') {
          __pwmWrite(32, Number(data.split(',')[2]));
        }
    });
  });

```