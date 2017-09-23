# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

上接[《一分钟：界面跳转》](https://www.gitbook.com/book/dragon8github/android-one-minute/edit#/edit/master/yi-fen-zhong-ff1a-jie-mian-tiao-zhuan.md?_k=u2qtv6)

1、在界面A发送数据的核心代码：

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
                intent.putExtra("first_name", "Hello");
                intent.putExtra("last_name", "word");
                startActivity(intent);
            }
        });
    }
}
```

2、在界面B接收数据的核心代码：

```java
package com.example.lee.myapplication;
import android.content.Intent;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.widget.TextView;
public class test extends AppCompatActivity {
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.test);
        Intent intent =  getIntent();
        String first_name =  intent.getExtras().get("first_name").toString();
        String last_name =  intent.getExtras().get("last_name").toString();
        ((TextView) findViewById(R.id.textView)).setText(first_name + last_name);
    }
}
```

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

