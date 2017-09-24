# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

上接[《一分钟：界面跳转》](https://www.gitbook.com/book/dragon8github/android-one-minute/edit#/edit/master/yi-fen-zhong-ff1a-jie-mian-tiao-zhuan.md?_k=0mpcd3)的知识点

这次我们用打开Uri的方式来打开界面（Activity）。

1、首页的代码：

```java
package com.example.lee.myapplication;
import android.content.Intent;
import android.net.Uri;
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
                intent.setAction("abc");
                intent.setData(Uri.parse("hello://world.com"));
                startActivity(intent);
            }
        });
    }
}
```

2、AndroidManifest.xml的配置：

```java
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
        <activity android:name=".test">
            <intent-filter>
                <action android:name="abc"/>
                <category android:name="android.intent.category.DEFAULT"/>
                <data android:scheme="hello" android:host="world.com" />
            </intent-filter>
        </activity>
    </application>
    <uses-permission android:name="android.permission.CALL_PHONE"></uses-permission>
</manifest>
```

知识点：

1、在 AndroidManifest.xml 中通过配置 action 和 scheme / host，就可以在代码中，用 setAction + setData\(uri\) 来跳转界面了；

2、在demo中没有体现出来，但事实上，如果出现不同的 activity 却有相同的 scheme / host 的情况，也没关系，因为我们可以通过代码setAction来告诉程序，应该读取哪个activity 下面的scheme / host。

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

