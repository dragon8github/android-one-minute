# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

1、新建/src/main/assets/index.html

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <button onclick="fuck()">点我调用Android的程序 - 跳转Android页面</button>
    <p><a href="user://login">通过uri方式打开</a></p>
</body>
<script type="text/javascript">
    var fuck = function() {
        window.abc.goToLoginPage();
    }
</script>
</html>
```

2、新建一个预跳转页面login.xml 和 login.java，空白页面即可。

3、在 AndroidManifest.xml 中注册 login页面。

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
        <activity android:name=".login">
            <intent-filter>
                <action android:name="android.intent.action.VIEW"/>
                <category android:name="android.intent.category.DEFAULT"/>
                <category android:name="android.intent.category.BROWSABLE"/>
                <data android:scheme="user" android:host="login" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

4、首页MainActivity的java代码：

```java
package com.example.lee.myapplication;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.webkit.JavascriptInterface;
import android.webkit.WebSettings;
import android.webkit.WebView;
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        final WebView w = (WebView)findViewById(R.id.webview);
        WebSettings ws = w.getSettings();
        ws.setAppCacheEnabled(true);
        ws.setJavaScriptEnabled(true);
        w.addJavascriptInterface(this, "abc");
        w.loadUrl("file:///android_asset/index.html");
    }
    @JavascriptInterface
    public void goToLoginPage(){
        this.runOnUiThread(new Runnable() {
            @Override
            public void run() {
               Intent intent = new Intent();
               intent.setClass(MainActivity.this, login.class);
                startActivity(intent);
            }
        });
    }
}
```

运行模拟器，点击webView中的页面和button 都可以跳转到login页面。

其中，button调用的是Android的代码。而&lt;a href="user://login"&gt;等同于是《[一分钟：用Uri的方式打开界面（Activity）](/123)》。但在index.html中想使用这种Uri跳转方式，必须在AndroidManifest.xml 中对Login进行一定配置：

```java
<activity android:name=".login">
    <intent-filter>
        <action android:name="android.intent.action.VIEW"/>
        <category android:name="android.intent.category.DEFAULT"/>
        <category android:name="android.intent.category.BROWSABLE"/>
        <data android:scheme="user" android:host="login" />
    </intent-filter>
</activity>
```



---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

