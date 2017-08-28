# 一分钟目标

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

> 打开 SDK Manager.exe 闪退

1、找到android.bat，在源码处找到

```bash
set java_exe= 
call lib\find_java.bat
```

改为

```
set java_exe=C:\Program Files\Java\jdk1.8.0_121\bin\java.exe
```

2、找到

```
for /f %%a in ('%java_exe% -jar lib\archquery.jar') do set swt_path=lib\%%a
```

改为

```
set swt_path=lib\x86_64
```



> 打开 AVD Manager.exe 闪退

找到C:\android-sdk-windows\tools\lib\find\_java.bat 修改源码，

1、找到43-44行，将

```
for /f "delims=" %%a in ('"%~dps0\find_java%arch_ext%.exe" -s') do set java_exe=%%a
if not defined java_exe goto :CheckFailed
```

修改为

```
set java_exe=C:\Program Files\Java\jdk1.8.0_121\bin\java.exe
```

2、找到49-50行，将

```
for /f "delims=" %%a in ('"%~dps0\find_java%arch_ext%.exe" -s -w') do set javaw_exe=%%a
if not exist "%javaw_exe%" set javaw_exe=%java_exe%
goto :EOF
```

修改为

```
set javaw_exe=C:\Program Files\Java\jdk1.8.0_121\bin\java.javaw_exe
```

> 第一次打开Android Studio 提示 “unable to access android sdk add-on list”





---

# 一分钟赞赏

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

---

# 一分钟指责

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

