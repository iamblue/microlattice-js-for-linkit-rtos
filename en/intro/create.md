# How to create Microlattice.js for MT7687 project

#### Prerequisite for Windows developer

**If you are Mac/linux developer, you can skip this section.**

For windows developer, please prepare the following:
* Install [msys2](https://msys2.github.io/).
* Install [mbed driver](https://developer.mbed.org/handbook/Windows-serial-configuration).
* Open msys2 and input:
```
update-core
```
* Install some msys2 package:
```
pacman -S tar unzip
pacman -S make
pacman -S git
pacman -S wget
```

### Set up Microlattice.js development environment

* You must have Node.js (0.10.32 ~ 4.X.X) enviropnment to continue.
  * mac/linux 用戶請用 [nvm](https://github.com/creationix/nvm) 安裝
  * windows 用戶請至 [這裏下載4.X.X](https://nodejs.org/en/) 版本
* Open command line tool and input:
```
npm install microlattice -g
```
* Create a folder called **testSDK**:
```
mkdir testSDK
```
* Go to the testSDK folder:
```
cd testSDK
```
* Create a microlattice project by input:
```
ml create
```
* Edit **featureConfig.json**:
```
{
  "IC_CONFIG": "mt7687",
  "BOARD_CONFIG": "mt7687_hdk"
}
```
* npm install ml-mt7687-config --save
* ml init:mt7687
* npm i

## Set up the 7687 project

| For Linus/ mac User | For Windows User |
| -- | -- |
| * Download the latest LinkIt 7687 [3.3.1 SDK](https://cdn.mediatek.com/download_page/index.html?platform=RTOS&version=v3.3.1&filename=LinkIt_SDK_V3.3.1_public.tar.gz). | * Download the latest LinkIt 7687 [3.3.1 SDK](https://cdn.mediatek.com/download_page/index.html?platform=RTOS&version=v3.3.1&filename=LinkIt_SDK_V3.3.1_public.tar.gz). |
| * Put the downloaded **LinkIt_SDK_V3.3.1_public.tar.gz** into the sdk folder in your project. | * Put the downloaded **LinkIt_SDK_V3.3.1_public.tar.gz** into the sdk folder in your project. |
| Skip | Download the [gcc](https://launchpad.net/gcc-arm-embedded/4.8/4.8-2014-q3-update/+download/gcc-arm-none-eabi-4_8-2014q3-20140805-win32.zip) and rename it as **gcc-arm-none-eabi.zip**. Put the **gcc-arm-none-eabi.zip** file into your project sdk folder as well. |
| Copy cache file:`cp ./node_modules/ml-mt7687-config/templates/v3.3.1_out.zip ./sdk` | Copy cache file:`cp ./node_modules/ml-mt7687-config/templates/v3.3.1_out.zip ./sdk` |
|`npm run installEnv` | `npm run installEnv` |
|- | Copy the 4 files in sdk folder to **./sdk/tools/gcc/gcc-arm-none-eabi/** folder and cover the original ones. If there is any file conflict, remove the original ones and paste again.|
| -| Go to the **root** folder and input the following: `./windows.sh` |

## Launch a Hello World project
* Edit the **index.js** file and add the followng:
```
print('Hello world!');
```
* Connect your LinkIt 7687 to your computer.
* Give the following command: `npm run build`
* You will see **Hello world!** pops out in a while.
* Congratulation! You've completed the microlattice development environment set up and you are ready to build your Microlattice.js project in LinkIt 7687.