# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

上接：《一分钟：外壳webView的初体验》

1、先在/src/main 下创建一个 assets 文件夹。然后再 assets 中创建一个 index.html 页面，加入以下测试代码

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    I'm index.html
</body>
</html>
```

2、在后端代码：

```java
package com.example.lee.myapplication;
import android.content.res.AssetManager;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.webkit.WebSettings;
import android.webkit.WebView;
import java.io.IOException;
import java.io.InputStream;
public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        WebView w = (WebView)findViewById(R.id.webview);
        WebSettings ws = w.getSettings();
        ws.setAppCacheEnabled(true);
        ws.setJavaScriptEnabled(true);
        AssetManager assetManager=getAssets();
        try {
            InputStream inputStream =assetManager.open("index.html");
            byte[] buffer=new byte[inputStream.available()];
            inputStream.read(buffer);
            String html_content=new String(buffer,"utf-8");
            w.loadData(html_content,"text/html","utf-8");
            inputStream.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

![](/assets/htmlasdasdasd.png)

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

