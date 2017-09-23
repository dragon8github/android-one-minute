# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

一、打开页面

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
                intent.setAction(intent.ACTION_VIEW);
                intent.setData(Uri.parse("https://www.baidu.com/"));
                startActivity(intent);
            }
        });
    }
}
```

二、打电话与权限设置

1、先在 AndroidManifest.xml 设置权限，加入以下代码，注意是和&lt;applicationapplication /&gt;同级的：

```
<uses-permission android:name="android.permission.CALL_PHONE"></uses-permission>
```

2、具体代码：

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
                intent.setAction(intent.ACTION_CALL);
                intent.setData(Uri.parse("tel://123456"));
                startActivity(intent);
            }
        });
    }
}
```

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

