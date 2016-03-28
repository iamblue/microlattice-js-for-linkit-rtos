# 如何創建 Microlattice.js 如何創建 


## 步驟
* 請先具備好 Node.js (> 0.10.32 以上)環境
* npm install microlattice -g
* 創建一個新的資料夾並進去: mkdir testSDK && cd testSDK
* ml create
* 編輯 featureConfig.json:
``` bash
{
  "IC_CONFIG": "mt7687",
  "BOARD_CONFIG": "mt7687_hdk"
}
```
* npm install ml-mt7687-config --save
* ml init:mt7687
* npm i

## 至 MTK 官網下載 SDK

* 請參考此步驟
* 將下載的 rar 檔，放入此專案的 /sdk folder 之中
* `npm run installEnv`

## 完成環境安裝後，來啟動 Hello world 吧！
* 編輯 index.js 中的內容為下：
``` bash
print('Hello world!');
```
* 接下來，把 7687 與您的電腦連接，再輸入: npm run build
* 過一會即可以看到 Hello world !