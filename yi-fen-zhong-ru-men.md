# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

进入项目路径：app/res/layout/activity\_main.xml，将下面的代码完全复制进去。然后运行模拟器查看

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="24dp"
        android:text="@string/app_name"
        />
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content">
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/btn1_name"
            />
        <Button
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/btn2_name"
            />
    </LinearLayout>
</LinearLayout>
```

![](file:///C:\Users\Lee\AppData\Roaming\Tencent\Users\928532756\QQ\WinTemp\RichOle\EY~4I~1A4%28U%29AKO[O[7_F]M.png)![](/assets/EY~4I~1A4%28U%29AKO[O[7_F]M.png)

### 你学会的知识点：

1. 元素的标签，如LinearLayout、TextView、Button等
2. 元素的属性，如layout\_width、orientation、text、padding等
3. 创建和使用字符串资源，在项目路径app/res/values/strings.xml可查看和定义，然后代码中通过@string/btn1\_name引用

### 1、android:layout\_width 和 android:layout\_height 属性：

| 属性 | 内容 |
| :---: | :---: |
| match\_parent | 视图与其父视图大小相同。 |
| wrap\_content | 视图将根据其展示的内容自动调整大小。 |

### 2、android:orientation 属性：

它决定两者的子组件  
是水平放置还是垂直放置。根 LinearLayout 是垂直的，子 LinearLayout 是水平的。

| 属性 | 内容 |
| :---: | :---: |
| vertical | 垂直 |
| horizontal | 水平 |

### 3、 android:padding 属性：

为元素增加内边距。即除内容本身外，还需增加额外指定量的空间。这样屏幕上显示的问题与按钮之间便会留有一定的空间，使整体显得更为美观。 （不理解dp的意思？dp即density-independent pixel，指与密度无关像素，稍后的章节有它的概念介绍 ）

### 4、android:text 属性：

TextView 与 Button 组件具有 android:text 属性。该属性指定组件要显示的文字内容。

如 android:text="Fuck" ，但这通常不是个好主意。比较好的做法是：将文字内容放置在独立的字符串资源XML文件中（项目路径**app/res/values/strings.xml**），然后引用它们。这样也便于对应用进行本地化。

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

