# lantern-for-mac

这是一款破解版的蓝灯VPN软件，我也是从别的地方clone下来的。最近国内vpn基本上都销声匿迹了，很少见到。

在编译过程中你需要知道的有以下几个方面：  
首先找个顺手地方放工程，然后用git将工程clone下来

## 1. 装homebrew。
打开终端，复制粘贴以下命令就OK，中间可能需要输一次密码：

`ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`  

## 2. 找个地方把lantern从GitHub上clone下来  

`git clone --depth=1 https://github.com/getlantern/lantern.git`  

-------------
## 3. 在同一个终端中 装go、node、gulp、appdmg、svgexport一堆  

`brew install go`</br>
`brew install node`</br>
`npm i gulp-cli -g`</br>
`npm install -g appdmg`</br>
`npm install -g svgexport`</br>  

--------------
## 4. 编译Mac版lantern  

`cd lantern`
`export VERSION=9.9.9`
`make darwin`

编译的时候可能会出现两个错误
![编译报错如图所示](error.png)  

在lantern文件夹对应路径中找到红框中四处，把MaxIdleTime改为IdleConnTimeout，然后把下面紧接的调用EnforceMaxIdleTime()这个方法的语句注释掉。就改这两个文件中的4行就行。重新编译。
