# 如何使用 MCS FOTA

* 首先請至 MCS 創建好一個 test device.
* 請參考這個 [創建好 ml 專案] (https://iamblue.gitbooks.io/microlattice-js-for-linkit-rtos/content/zh-TW/intro/create.html)
* 到您創建好的 ml 專案根目錄下: `npm install ml-mcs --save`
* 至 featureConfig.json 添加: `ml-mcs: true`
* 接下來至 index.js 參考這段範例程式碼：

``` js
  __pinmux(35, 8);

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
        // FOTA 的 data parser 部分已經有在 lib 底層整好
        print(data);
      }
    );
  });

```
* 輸入 `npm run build` 燒 code 進去 MT7687 (燒 code 方式請注意各個開發板的不同)
* 回到 MCS 的 test device detail page.
* 點選 firmware ，並上傳您所指定的 image 即可.