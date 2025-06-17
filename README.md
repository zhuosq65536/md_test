# AQCV GUI

## 开始

该项目配置教程如下。

## 软件环境配置

```
Windows 11操作系统

Visual Studio 2019（其中安装插件：QT Visual Studio Tools)

Qt5.15.2

swigwin-4.3.1

cmake>3.19
```



## 系统环境变量

```
变量名 ：CMAKE_PREFIX_PATH

变量值：D:\ProgramData\QT\5.15.2\msvc2019_64\lib\cmake(替换为你本地的
```

目的是让程序可以找到在该路径下的Qt5文件夹下的Qt5Config.cmake文件。

```
变量名 ：QT_PLUGIN_PATH

变量值：D:\ProgramData\QT\5.15.2\msvc2019_64\plugins(替换为你本地的)
```

目的是让程序可以找到在该路径下的platforms文件夹下的qwindows.dll文件。

## 操作顺序

打开Visual Studio 2019，不要打开任何项目先进入主界面，然后通过“**文件**->**打开**->**CMake**"的方式打开该项目中

**CmakeLists.txt**文件,即可成功打开项目。

这时右侧可以在解决方案资源管理器中看到所有的项目文件，通过“右键**解决方案资源管理器**中的**CmakeLists.tx**t文件

->**生成**”的方式进行cmake生成，稍等一会即可发现目标全部生成。

部分代码使用了一些图片用做测试，图片可以找前辈要，将对应的图片放在对应的位置中即可，例如在

install\bin\Release\images目录下放入test_image3.jpg。