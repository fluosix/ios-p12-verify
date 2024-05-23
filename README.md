# ios-p12-verify
本程序能快速验证苹果证书是否被吊销，以及ios证书和描述文件是否匹配。

压缩包中有两个文件，如果是mac系统，使用ios-p12-verify。如果是windows系统，使用ios-p12-verify.exe。

1.执行可执行文件ocsp-server或者ocsp-server.exe \
mac
```shell
ocsp-server -p12 /path/to/ios.p12 -pw 123 -mpv /path/to/ios.mobileprovision
```
windows
```shell
ocsp-server.exe -p12 /path/to/ios.p12 -pw 123 -mpv /path/to/ios.mobileprovision
```
其中-p12是证书文件路径，-pw是证书密码，-mpv是描述文件路径。

2.结果会显示在控制台上

![img.png](img.png)

certStatus有三种状态，分别是：Revoked、Good、Unknown。

Revoked：证书已经被吊销。
Good：证书正常。
Unknown：未知状态。

isMatch 表示证书和描述文件是否匹配，如果匹配，返回true，否则返回false。


