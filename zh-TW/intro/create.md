# 如何創建 Microlattice.js for MT7687 專案


#### windows 開發者必做幾個項目
* 安裝 [msys2](https://msys2.github.io/)
* 安裝 [mbed driver](http://mbed.org/handbook/Windows-serial-configuration)
* 打開安裝好的 msys2
* 更新 msys2, 輸入:
```
update-core
```
* 安裝 uzip 和 make
```
pacman -S tar unzip
pacman -S make
```

#### Linux/Mac 開發者直接進行以下項目

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

* [請參考此步驟](https://iamblue.gitbooks.io/mt7687-on-linkit-rtos-ebook-for-community/content/zh-TW//intro/downloadSDK.html)
* 將下載的 rar 檔，放入此專案的 ./sdk folder 之中
* (windows 使用者請多做此步驟) 至此[ 下載 gcc ](https://launchpad.net/gcc-arm-embedded/4.8/4.8-2014-q3-update/+download/gcc-arm-none-eabi-4_8-2014q3-20140805-win32.zip)並把檔案改名為 `gcc-arm-none-eabi.zip` 並丟到 ./sdk
* copy cache file : `cp ./node_modules/ml-mt7687-config/templates/v3.0.0_out.zip ./sdk` (注意 v3.0.0 記得改為您的 sdk version)
* `npm run installEnv`
* (windows 使用者請多做此步驟) 至 ./sdk 把 gcc-arm-none-eabi.zip 底下四個資料夾強制覆蓋 ./sdk/tools/gcc/gcc-arm-none-eabi/ 下的四個資料夾，若發生當案衝突請將原來四個資料夾全刪除再覆蓋.
* (windows 使用者請多做此步驟) 至 project 根目錄輸入 `./windows.sh`

## 完成環境安裝後，來啟動 Hello world 吧！
* 編輯 index.js 中的內容為下：
``` bash
print('Hello world!');
```
* 接下來，把 7687 與您的電腦連接，再輸入: `./build.sh`
* 過一會即可以看到 Hello world !
* ps. 若出現一些錯誤請再做一次 `./build.sh` 即可。