# AQCV GUI

## 开始
## 环境配置：

VS2019（其中安装QT Visual Studio Tools)
Qt5.15.2
swigwin-4.3.1
cmake大于3.19

## 问题1：cmake报错

```markdown
CMake Error at utils/CMakeLists.txt:5 (find_package):
Could not find a package configuration file provided by "QT" with any of
the following names:
Qt6Config.cmake
qt6-config.cmake
Qt5Config.cmake
qt5-config.cmake
Add the installation prefix of "QT" to CMAKE_PREFIX_PATH or set "QT_DIR" to
a directory containing one of the above files.  If "QT" provides a separate
development package or SDK, be sure it has been installed.
```
大致意思是找不到下面四个文件的任何一个。
解决办法：
新增一个环境变量：
![image-20250616170537850](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20250616170537850.png)
然后重新cmake即可（这里我是通过系统文件夹中打开**终端**的方式运行cmake的)。

## 问题2：cmake生成的调试目标不全，![image-20250616171532460](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20250616171532460.png)
解决办法：
我最初并没有通过“文件->打开->CMake"的方式打开该项目，所以我尝试把目前的缓存全部删除，然后通过“文件->打开->CMake"的方式打开该项目中CmakeLists.txt文件，这里通过“右键**解决方案资源管理器**中的**CmakeLists.tx**t文件->**生成**”的方式进行cmake生成。然后发现调试目标全部生成，问题解决。

## 问题3：找不到windows平台插件
```markdown
qt.qpa.plugin: Could not load the Qt platform plugin "windows" in "" even though it was found. This application failed to start because no Qt platform plugin could be initialized. Reinstalling the application may fix this problem. Available platform plugins are: windows.
```
解决办法：根据报错信息添加一个环境变量
![image-20250616175146012](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20250616175146012.png)
目的是让程序可以找到在该路径下的platforms文件夹下的qwindows.dll文件。

## 问题4：找不到图片路径
解决办法：在对应的路径下放入对应的图片文件即可。（在install\bin\Release\images目录下放入test_image3.jpg)
