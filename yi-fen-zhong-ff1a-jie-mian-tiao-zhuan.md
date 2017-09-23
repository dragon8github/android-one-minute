# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

1、新建一个test.java类

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

2、在res/layout中新建一个Layout resource file作为测试界面test.xml

3、在主页中，编写跳转代码

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

