# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

一、需要先找到要打开的包名和界面（activity）。

找到模拟器的Dev Tool -&gt;  Package Browser -&gt;  找到你将要打开的APP，如时钟Clock。

如下图所示，com.android.deskclock 就是包名。Activities 下的列表，就是可选的打开界面（activity）, 但不一定每个都可以打开，毕竟有一些界面需要逻辑或数据才可以正常打开。所以这里我选择第一个：DeskClock。 ![](/assets/12312312.png)

二、编写代码:

```
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
                intent.setClassName("com.android.deskclock", "com.android.deskclock.DeskClock");
                startActivity(intent);
            }
        });
    }
}
```

![](/assets/123ddss.png)

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

