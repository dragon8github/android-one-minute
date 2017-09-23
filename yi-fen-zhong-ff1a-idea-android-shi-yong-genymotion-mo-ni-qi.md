# 一分钟目标

接下来要让Android / IDEA 和 Genymotion 结合，这需要编辑器插件的支持。

**按下CTRL + ALT + S &gt; Plugins &gt; Browse repositories.. &gt; 输入Genymotion &gt; install &gt; 重启IDEA**![](/assets/sadazzxc.png)

重启完IDEA之后，我们需要显示开启Genymotion的按钮：顶部菜单 &gt; View &gt; Toolbar

![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520174135994-1573657581.png)

点击一下上图最后一个图标，配置一下genymotion.exe的所在目录即可，比如我的是C:\Genymotion\

弹出一个genymotion的模拟器列表窗口。我们使用上面安装的Google Nexus 4.2.2.按下【start】按钮开启模拟器。

![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520174656807-2049810752.png)

**请注意，一次只能开启一台模拟器，所以你需要先关闭所有genymotion的模拟器，不然是无法点击【start】按钮的!**

![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520180524353-325925758.png)

模拟器开启成功后，先放着不关闭，然后返回IDEA。在头部菜单栏 &gt; Run &gt; Run.. &gt; 0.Edit Configurations:![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520180822744-1719637425.png)

如果没有Android Application的话则新建一个，按照默认的配置即可。然后点击【Run】按钮。![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520181106728-1126926317.png)

选择我们**已启动**的模拟器。点击【OK】，进行编译！

![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520181109619-1704565810.png)

报错1：**【This app has been built with an incorrect configuration. Please configure your build for VectorDrawa】**

（1）将build.gradle中的版本改为2.0.0，如下图所示。

![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520201228119-758849543.png)

然后重新编译一下：顶部菜单 &gt; Build &gt; Rebuild Project

继续报错：**【Gradle version 2.10 is required. Current version is 2.8. If using the gradle wrapper, try editing the distributionUrl in E:\RX\gradle\wrapper\gradle-wrapper.properties to gradle-2.10-all.zip  】**

（2）打开项目目录，右键项目 &gt; show in Explorer![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520201550369-1393360116.png)

打开如：**C:\Users\Lee\IntelliJIDEAProjects\MyApplication\gradle\wrapper\gradle-wrapper.properties**，如图所示，进行修改即可

![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520201807338-1114036781.png)

重新编译然后运行项目

报错2：【未知】

打开 app &gt; build.gradle 查看里面大部分的SdkVersion 都指向了25.这是因为项目默认使用了Android 7.x 而它的版本号就是25，前面我们也说到了。我们使用了Android 6.X，版本号为23 才能正常运行一些东西。所以这里大部分的数据请修改为23.但请先别急着修改。先进行下面一个操作

我们先需要运行Android SDK中的管理工具【SDK Manager.exe】。在Tools栏目中选择23的版本。这里推荐23.0.3版本。然后进行安装。

![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520202806978-1162948577.png)

回到build.gradle，请查找并对以下几处进行修改:

```
compileSdkVersion 23
buildToolsVersion "23.0.3"
targetSdkVersion 23
compile 'com.android.support:appcompat-v7:23.0.0'
```

解决完所有错误之后，这是正确的效果图：![](http://images2015.cnblogs.com/blog/922445/201705/922445-20170520202047775-1848374856.png)

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

