```
一分钟目标
```

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

1、在主界面加入一系列控件：webView、button、TextVew；

2、在src/main/assets/index.html 中加入以下代码，用于测试js和Android交互；

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <button onclick="setAndroidTextView()">点我调用Android的程序</button>
    <input type="text" id="input">
</body>
<script type="text/javascript">
    window.showname = function (name) {
        document.getElementById("input").value = name.toString();
    }
    window.setAndroidTextView = function() {
        var v = document.getElementById("input").value;
        window.abc.SetTextView(v);
    }
</script>
</html>
```

3、MainActivity.java的核心代码

```java
package com.example.lee.myapplication;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.webkit.JavascriptInterface;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.widget.Button;
import android.widget.TextView;
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
        Button btn = (Button)findViewById(R.id.button);
        btn.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View v) {
                w.loadUrl("javascript:showname('fuckyou')");
            }
        });
    }
    @JavascriptInterface
    public void SetTextView(final String txt){
        this.runOnUiThread(new Runnable() {
            @Override
            public void run() {
                TextView tv = (TextView)findViewById(R.id.textView);
                tv.setText(txt);
            }
        });
    }
}
```

打开模拟器，当我们点击Android的button和index.html的button后，产生的界面大致如下：

![](/assets/fuckyou129319283.png)

知识点：

1、需要给 JavaScript 调用的函数必须是开启线程 this.runOnUiThread + run\(\)；

2、需要给 JavaScript 调用的函数必须加入注解：@JavascriptInterface；

3、必须使用 w.addJavascriptInterface\(this, "abc"\); 将当前的类注册为 "abc" 给 JavaScript 调用。所以js中才可以使用window.abc.SetTextView 来调用。

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

