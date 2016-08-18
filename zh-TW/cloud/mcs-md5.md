# 上傳資料至 mcs 基礎教學

### 本篇範例流程為：

* 從 mcs 接收到一段 string.
* 將此 string 經過 md5 編譯拿到一段文字.
* 再接此編譯後的文字上傳至 mcs.

### 流程
* 首先請至 MCS 創建好一個內有 string (string control datachannel) 和 md5 (string display datachannel) 的 test device.
* 請參考這個 [創建好 ml 專案](https://iamblue.gitbooks.io/microlattice-js-for-linkit-rtos/content/zh-TW/intro/create.html)
* 到您創建好的 ml 專案根目錄下:
```
  npm install ml-mcs --save
  npm install ml-md5 --save
```
* 至 featureConfig.json 添加:
```
  ml-mcs: true,
  ml-md5: true
```
* 接下來至 index.js 參考這段範例程式碼：

``` js
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
        if (data.split(',')[1] === 'string') {
          var string = __md5(data.split(',')[2]);
          __mcsSend('md5', string);
        }
      }
    );
  });

```
* 輸入 `npm run build` 燒 code 進去 MT7687 (燒 code 方式請注意各個開發板的不同)
* 回到 MCS 的 test device detail page.
* 在 'string' 的卡片上輸入一段文字送出，接下來就會在 md5 卡片那邊看到 87 傳回來的字串.