# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

进入项目路径：**app/res/layout/activity\_main.xml**，为两个button添加“ID”属性。@+id就和@string一样，是为了引用app/res/values/strings.xml的定义

```java
<Button
    android:id="@+id/btn1_name"
    ...
/>
<Button
    android:id="@+id/btn2_name"
    ...
/>
```

进入项目路径：app/java/项目名/MainActivity， 将下面的代码完全复制进去。运行模拟器

（AKA:  先将鼠标光标聚焦在关键字上，然后通过Alt + Enter快捷键可以快速智能引入import依赖包）

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

![](/assets/import.png)

### 你学会的知识点：

1. 通过“ID”属性，绑定元素的事件“click”绑定;
2. Toast组件的使用;
3. 依赖包的引用全靠Alt + Enter快捷键智能引入（鼠标光标聚焦在关键字上）

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

