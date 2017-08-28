# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

> #### 打开 SDK Manager.exe 闪退

1、找到android.bat

```ruby
# 第一处查找
set java_exe = call lib\find_java.bat

# 替换 
set java_exe=C:\Program Files\Java\jdk1.8.0_121\bin\java.exe
```

2、继续查找

```ruby
# 第二处查找
for /f %%a in ('%java_exe% -jar lib\archquery.jar') do set swt_path=lib\%%a

# 替换
set swt_path=lib\x86_64
```



> #### 打开 AVD Manager.exe 闪退

1、找到C:\android-sdk-windows\tools\lib\find\_java.bat 修改源码

```ruby
# 找到43-44行
for /f "delims=" %%a in ('"%~dps0\find_java%arch_ext%.exe" -s') do set java_exe=%%a
if not defined java_exe goto :CheckFailed

# 替换为
set java_exe=C:\Program Files\Java\jdk1.8.0_121\bin\java.exe
```

2、继续查找

```ruby
# 找到49-50行
for /f "delims=" %%a in ('"%~dps0\find_java%arch_ext%.exe" -s -w') do set javaw_exe=%%a
if not exist "%javaw_exe%" set javaw_exe=%java_exe%
goto :EOF

# 替换为
set javaw_exe=C:\Program Files\Java\jdk1.8.0_121\bin\java.javaw_exe
```



> #### 第一次打开Android Studio 提示 “unable to access android sdk add-on list”

不要着急，解决方法是：点击cancel。然后重启Android studio。这时就会自动提示你下载Android SDK了。

如果没有提示下载的话。那么就这样做：在自己安装的目录下找到：bin\idea.properties打开这个文件末尾添加一行disable.android.first.run=true。之后再次运行就可以下载依赖的sdk了

下载SDK的过程中请确保开启fq。因为下载的资源在国外，如果没有fq的话某些资源会下载失败。那么你的Android SDK也无法使用前功尽弃。

---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

