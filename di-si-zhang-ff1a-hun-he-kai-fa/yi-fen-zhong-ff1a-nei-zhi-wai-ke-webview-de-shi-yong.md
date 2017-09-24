# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

1、在layout中加入一个WebView控件，并为它设置一个@+id/webview![](/assets/12312dxvvnmm.png)2、在 AndroidManifest.xml 中加入访问Inter的权限，否则待会无法访问url

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
    <uses-permission android:name="android.permission.INTERNET"></uses-permission>
</manifest>
```

3、在MainActivity.java中编写代码：

```java
package com.example.lee.myapplication;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.webkit.WebSettings;
import android.webkit.WebView;
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        WebView w = (WebView)findViewById(R.id.webview);
        WebSettings ws =  w.getSettings();
        ws.setAppCacheEnabled(true);
        ws.setJavaScriptEnabled(true);
        w.loadUrl("https://www.baidu.com");
    }
}
```

![](/assets/292193283293901.png)

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

