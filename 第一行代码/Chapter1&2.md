# Chapter 1 概述
1、Android大致分为四层架构：**Linux内核层、系统运行库层、应用框架层、应用层**。

2、Android系统四大组件：活动、服务、广播接收器、内容提供器。

3、使用Log而不是System.out，因为System.out日志级别不区分、不能加过滤器等。Log日志级别：verbose, debug, info, warn, error.

# Chapter 2 活动（重点）
1、所有活动都要在AndroidManifest.xml文件中注册才能生效。

2、Toast将短小的信息通知给用户，一段时间后会消失。

3、Intent是各组件之间交互的一种方式，可以指明当前组件要执行的动作以及组件之间传递数据。用法分为显式Intent和隐式Intent。

显式Intent明确指定了要激活的组件是哪个组件，一般在应用程序内部使用，但耦合度很高。

隐式Intent通过清单文件中配置IntentFilter来实现，当一个应用要激活另一个应用的Activity时（不知道源码），只能使用隐式Intent，它会根据action, category, URI和数据类型找到最合适的组件处理该Intent。但是隐式Intent会搜索所有可用的IntentFilter来查看是否有匹配的内容，效率比较低。

Intent还可以在启动活动的时候传递数据，利用genIntent获取上一个活动的Intent数据，startActivityForResult和onActivityResult分别用于启动下一个活动和得到返回数据。

4、**活动的生命周期**

活动状态：运行、暂停、停止、销毁

![活动状态转换](https://github.com/WilliumP/ReadingNotes/blob/master/res/1.png)

完整生存期：onCreate() 和 onDestroy()之间，前者完成各种初始化操作，后者完成释放内存操作。

可见生存期：onStart() 和 onStop()之间，前者对资源进行加载，后者释放资源。

前台生存期：onResume() 和 onPause()之间，此时活动可以和用户进行交互。

5、Bundle参数传递/保存数据，onSaveInstanceState()回调方法可以在活动回收前调用，而且它携带Bundle类型的参数。Intent和Bundle可以结合起来传递数据。

6、**活动的启动模式**

![standard模式](https://github.com/WilliumP/ReadingNotes/blob/master/res/standard.png)

