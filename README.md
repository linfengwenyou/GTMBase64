GTMBase64
=========

Base64加解密

使用方法：

1）丢入ios项目。
【注意】开启ARC的同学注意
解决方法：`-fno-objc-arc`

2）在要使用GTMBase64的地方#import "GTMBase64.h"引入头文件

3）下面详细说明：

常用的方法，有下面几个：
```
+ (NSString*)md5_base64: (NSString *) inPutText;
+ (NSString*)encodeBase64String:(NSString *)input;
+ (NSString*)decodeBase64String:(NSString *)input;
+ (NSString*)encodeBase64Data:(NSData *)data;
+ (NSString*)decodeBase64Data:(NSData *)data;
```

#### 使用注意，如果有使用Xcode的Address Sanitizer功能可能会出现问题：【未解决】
```
* thread #1, queue = 'com.apple.main-thread', stop reason = Heap buffer overflow
```

问题定位：对于单字符数据进行加密会出现问题，多字符不会  eg: @"3" @"a" 会出现问题
