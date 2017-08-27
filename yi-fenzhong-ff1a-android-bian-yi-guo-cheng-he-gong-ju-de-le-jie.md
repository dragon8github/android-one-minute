# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

### Android 编译过程

整个编译过程中，Android开发工具将资源文件、 代码以及AndroidManifest.xml文件 （包含应用的元数据） 编译生成.apk文件。 .apk应用要在模拟器上运行，.apk文件还需以debug key签名。 

![](file:///C:\Users\Lee\AppData\Roaming\Tencent\Users\928532756\QQ\WinTemp\RichOle\6$%D9Q}T0%~5RO0]N~%28L$3N.png)![](file:///C:\Users\Lee\AppData\Roaming\Tencent\Users\928532756\QQ\WinTemp\RichOle\6$%D9Q}T0%~5RO0]N~%28L$3N.png)![](/assets/6$%D9Q}T0%~5RO0]N~%28L$3N.png)

### Android 编译工具

截至目前， 我们所看到的项目编译都是在Android Studio里执行的。 编译功能已整合到IDE中，  
IDE负责调用aapt等Android标准编译工具，但编译过程本身仍由Android Studio管理。

有时，出于种种原因，可能需要脱离Android Studio编译代码。最简单的方法是使用命令行  
编译工具。现代Android编译系统使用Gradle编译工具。

要使用Gradle，请切换到项目目录并执行以下命令：

**$ ./gradlew tasks  
**

如果是Windows系统，执行以下命令：

**&gt; gradlew.bat tasks  
**

执行以上命令会显示一系列可用任务。你需要的是任务是installDebug，因此，再执行以下  
命令：

**$ ./gradlew installDebug  
**

如果是Windows系统，执行以下命令：

**&gt; gradlew.bat installDebug  
**

以上命令将把应用安装到当前连接的设备上，但不会运行它。要运行应用，需要在设备上手  
动启动。

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

