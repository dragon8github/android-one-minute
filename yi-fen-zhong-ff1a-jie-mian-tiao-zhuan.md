# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

1、在res/layout中新建一个Layout resource file作为测试界面test.xml。

2、在AndroidManifest.xml中，在&lt;application /&gt;内配置这个视图，加入 &lt;activity android:name=".test"&gt;&lt;/activity&gt;， 最终大致如下：

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.lee.myapplication" >
    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:supportsRtl="true"
        android:theme="@style/AppTheme" >
        <activity android:name=".MainActivity" >
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".test"></activity>
    </application>
</manifest>
```

3、新建一个test.java类，指向我们刚刚创建的test视图

```java
package com.example.lee.myapplication;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
public class test extends AppCompatActivity {
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.test);
    }
}
```

4、在主页中，编写跳转代码

```java
package com.example.lee.myapplication;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btn = (Button)findViewById(R.id.hello_btn);
        btn.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View v) {
                Intent intent = new Intent();
                intent.setClass(MainActivity.this, test.class);
                startActivity(intent);
            }
        });
    }
}
```

事实上，绑定的click事件也可以这样写。

```java
package com.example.lee.myapplication;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btn = (Button)findViewById(R.id.hello_btn);
        btn.setOnClickListener(new BtnClicker());
    }
    class BtnClicker implements View.OnClickListener{
        @Override
        public void onClick(View v) {
            Intent intent = new Intent();
            intent.setClass(MainActivity.this, test.class);
            startActivity(intent);
        }
    }
}
```

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

