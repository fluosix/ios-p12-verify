# ios-p12-verify

This program can quickly verify whether the Apple certificate has been revoked and whether the ios certificate and description file match.

There are two files in the compressed package. If it is a mac system, use ios-p12-verify. If it is a Windows system, use ios-p12-verify.exe.

mac
```shell
ocsp-server -p12 /path/to/ios.p12 -pw 123 -mpv /path/to/ios.mobileprovision
```

windows
```shell
ocsp-server.exe -p12 /path/to/ios.p12 -pw 123 -mpv /path/to/ios.mobileprovision
```

-p12 is the certificate file path, -pw is the certificate password, and -mpv is the description file path.

The results will be displayed on the console

![img.png](img.png)

certStatus has three states: Revoked, Good, and Unknown.

Revoked: The certificate has been revoked. Good: The certificate is normal. Unknown: Unknown status.

isMatch indicates whether the certificate and description file match. If they match, return true, otherwise return false.


