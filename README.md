# Flesh（果肉）

果肉一款福利满满的app，数据源[mzitu][3]，MD风格的界面。

组成
--------
1. 语言：Kotlin，Java
2. 网络请求：HttpUrlConnection
3. 数据库：Sqlite
4. 数据源：Jsoup
5. 第三方库：Glide

概述
--------
网络请求  
get
```java
val request = AsyncNetwork()
request.request(Constants.HOST_MOBILE_URL, null)
request.setRequestCallback(object : IRequestCallback {
    override fun onSuccess(httpURLConnection: HttpURLConnection?, response: String) {
        //todo
    }
})
```
post
```java
val request = AsyncNetwork()
request.request(Constants.HOST_MOBILE_URL, mutableMapOf())
request.setRequestCallback(object : IRequestCallback {
    override fun onSuccess(httpURLConnection: HttpURLConnection?, response: String) {
        //todo
    }
})
```
ProGuard
--------
```pro
-keep class org.jsoup.**{*;}
-keep public class com.ecjtu.netcore.jsoup.SoupFactory{*;}
-keep public class * extends com.ecjtu.netcore.jsoup.BaseSoup{*;}
-keep public class com.ecjtu.netcore.Constants{static <fields>;}
-keep public class com.ecjtu.netcore.model.**{*;}
-keep public class com.ecjtu.netcore.network.BaseNetwork{public <methods>;}
-keep public class * extends com.ecjtu.netcore.network.BaseNetwork{ public <methods>; }
-keep public interface com.ecjtu.netcore.network.IRequestCallback{*;}
-keep public class * extends com.ecjtu.flesh.ui.widget.ScrollAwareFABBehavior{*;}
```

Contributing
------------
contributors submmit pull requests.

Thanks
------
* The **Glide** [image loading framework][1] Flesh's image loader is based on.
* The **Bugly** [app monitoring tools][2] Flesh's log collector.
* Everyone who has contributed code and reported issues!

Author
------
KerriGan - mnsync@outlook.com or ethanxiang95@gmail.com

License
-------
[Apache2][4]

Disclaimer
---------
Only available for study and communication.If the flesh violate your rights,we can delete immediately violate to your rights and interests content.

[1]: https://github.com/bumptech/glide
[2]: https://bugly.qq.com/v2/
[3]: http://www.mzitu.com
[4]: https://github.com/Kerr1Gan/Flesh/blob/master/LICENSE
