# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

进入项目路径：**app/res/layout/activity\_main.xml**，为两个 button 添加 “ID” 属性。其余代码不变。

@+id 和 @string一样，是为了引用 app/res/values/strings.xml 的定义。

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
            android:id="@+id/btn1_name"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/btn1_name"
            />
        <Button
            android:id="@+id/btn2_name"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/btn2_name"
            />
    </LinearLayout>
</LinearLayout>
```

进入项目路径：app/java/项目名/MainActivity， 将下面的代码完全复制进去。运行模拟器

**（AKA:  先将鼠标光标聚焦在关键字上，然后通过Alt + Enter快捷键，然后选择import Class，可以智能引入依赖包）**

```java
package com.example.lee.geoquiz;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    private Button mTrueButton;
    private Button mFalseButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        mTrueButton = (Button) findViewById(R.id.btn1_name);
        mFalseButton = (Button) findViewById(R.id.btn2_name);

        mTrueButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(MainActivity.this, "Fuck", Toast.LENGTH_SHORT).show();
            }
        });

        mFalseButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(MainActivity.this, "You", Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

![]()

### 你学会的知识点：

1. 通过 “ID” 属性，绑定元素的事件 “click” 绑定;
2. Toast 组件的使用;
3. 依赖包的引用全靠 Alt + Enter 快捷键，然后选择 import Class 智能引入依赖包（鼠标光标聚焦在关键字上）

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

