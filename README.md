
## Android执行Perl

> Try to run perl scripts in Android Application

----
在执行本项目时碰到的错误：

```log
   com.licoba.testscript        W  Starting perl process
   com.licoba.testscript        E  Failed to start process: /data/user/0/com.licoba.testscript/files/perl/bin/perl
                                                                  java.io.IOException: Cannot run program "/data/user/0/com.licoba.testscript/files/perl/bin/perl" (in directory "/data/data/com.licoba.testscript"): error=13, Permission denied
```

![img.png](img.png)

是因为  ProcessBuilder  从Android 10 开始，就没办法执行Android私有目录下的任何可执行文件了
可以参考这个 https://stackoverflow.com/questions/60370424/permission-is-denied-using-android-q-ffmpeg-error-13-permission-denied


至于解决方案，在这里 https://stackoverflow.com/questions/60370424/permission-is-denied-using-android-q-ffmpeg-error-13-permission-denied

## 结论

1. 如果是没有root的手机，就没办法在App运行时，执行任何可执行二进制文件，都会提示没有权限。
2. 真要在Android App上执行perl脚本的话，建议通过 **自定义ROM** 来实现，权限足够高，可以随意操作。

---
【感谢】
- 原项目在这里：https://github.com/castaway/run-perl  

- 这是是一个十年前的项目，在Android App里面可以运行的Perl文件。