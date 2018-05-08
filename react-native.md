# react native安装教程
## 1. 安装node环境
1. 在 [node官网]: <https://nodejs.org/en/> 下载pkg包
![nodejs pkckage download](https://raw.githubusercontent.com/jinelei/markdowns/master/images/markdown/node.js.png)
  
下载完成后点击安装。
  
![nodejs install wizard](https://raw.githubusercontent.com/jinelei/markdowns/master/images/markdown/node-install-wizard.png)
  
安装完成打开终端，输入```node -v```确认是否安装成功。
  
![nodejs -v](https://raw.githubusercontent.com/jinelei/markdowns/master/images/markdown/node-v.png)

## 2. 安装Yarn、React Native的命令行工具（react-native-cli）

Yarn是Facebook提供的替代npm的工具，可以加速node模块的下载。React Native的命令行工具用于执行创建、初始化、更新项目、运行打包服务（packager）等任务。

```npm install -g yarn react-native-cli```

安装成功如下：

![install yarn react-native-cli](https://raw.githubusercontent.com/jinelei/markdowns/master/images/markdown/yarn-install.png) 

[可选]安装完yarn后同理也要设置镜像源：

```
yarn config set registry https://registry.npm.taobao.org --global
yarn config set disturl https://npm.taobao.org/dist --global
```


## 3. 配置android && ios

#### Android Studio
  
> Android Studio需要Java Development Kit [JDK] 1.8或更高版本。你可以在命令行中输入 javac -version来查看你当前安装的JDK版本。如果版本不合要求，则可以到官网上下载。

*ANDROID_HOME环境变量*

> 环境变量很重要！要不项目跑不起来。

*添加环境变量*
> 1. 编辑 /etc/profile, ~/.basr_profile, ~/.bashrc（作用域不同，自己根据需要选择）
> > 例如： vim ~/.bashrc
> 2. 载入环境变量： 通过source命令或者./
> >例如： source ~/.bashrc
> 3. 检查环境变量 通过echo命令或者env查看
> >例如： echo $ANDROID_HOME



#### Xcode

> React Native目前需要Xcode 8.0 或更高版本。你可以通过App Store或是到Apple开发者官网上下载。这一步骤会同时安装Xcode IDE和Xcode的命令行工具。虽然一般来说命令行工具都是默认安装了，但你最好还是启动Xcode，并在Xcode | Preferences | Locations菜单中检查一下是否装有某个版本的Command Line Tools。


## 4. Gradle Daemon

> 开启Gradle Daemon可以极大地提升java代码的增量编译速度。

```
    touch ~/.gradle/gradle.properties \
    && echo "org.gradle.daemon=true" \
    >> ~/.gradle/gradle.properties
```

## 5. 测试安装



```
    react-native init ProjectDemo
    cd ProjectDemo
    react-native run-android
```

> 你可以使用--version参数创建指定版本的项目。例如react-native init MyApp --version 0.44.3。注意版本号必须精确到两个小数点。

init命令默认会创建最新的版本，而目前最新需要下载boost库编译。此库体积庞大，在国内即便翻墙也很难下载成功，导致很多人无法正常运行iOS项目，中文网在论坛中提供了这些库的国内下载链接。如果你嫌麻烦，又没有对新版本的需求，那么可以暂时创建0.44.3的版本。


```
    react-native init ProjectDemo --verison 0.44.3
    cd ProjectDemo
    react-native run-ios/run-android
```