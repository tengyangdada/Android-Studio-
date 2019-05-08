## <center> Android欢迎你</center>
&nbsp;&nbsp;AndroidStudio是Google发布的用于Android的开发平台。系统基于 IntelliJ IDEA。类似 EclipseADT，Android Studio 提供了集成的 Android 开发工具用于开发和调试。Android Studio的开发环境和模式更加的丰富和便捷，能够支持多种语言，还可以为开发者提供测试工具和各种数据分析。  
&nbsp;&nbsp;Android应用程序主要使用Java语言编写，要用到开发工具集SDK（Software Development Kit，提供java编译工具、Android系统API等，可以直接在Android Studio中下载）。当应用程序中要直接访问硬件，或者需要提高运行效率时，需要将访问硬件、复杂逻辑部分使用C/C+ +实现。要在Android Studio中开发编译C/C+ +代码，需要用到工具集NDK（Native Development Kit，提供C/C+ +编译工具、API、打包工具等，可直接在Android Studio中下载）。使用NDK可以将C/C+ +源码编译成动态链接库，供Java调用。由于Java语言要调用C/C++函数需要用到JNI（Java Native Interface）技术，这就要求使用NDK开发C/C+ +时，C/C+ +源码要符合JNI规范要求。
</br>让我们一起进入Android的世界
### &nbsp;&nbsp;&nbsp;&nbsp;1.1&nbsp;&nbsp;Android系统架构
&nbsp;&nbsp;Android系统架构分为五层，从上到下依次是应用层、应用框架层、系统运行库层、硬件抽象层和Linux内核层。 
* **应用层**
</br>系统内置的应用程序以及非系统级的应用程序都是属于应用层。负责与用户进行直接交互，通常都是用Java进行开发的。

* **应用框架层**
</br>应用框架层为开发人员提供了可以开发应用程序所需要的API，我们平常开发应用程序都是调用的这一层所提供的API，当然也包括系统的应用。这一层的是由Java代码编写的，可以称为Java Framework。下面来看这一层所提供的主要的组件。

* **系统运行库层（Native)**
</br>系统运行库层分为两部分，分别是C/C++程序库和Android运行时库。下面分别来介绍它们。
</br>&nbsp;&nbsp;&nbsp;&nbsp;C+ +程序库：C/C+ +程序库能被Android系统中的不同组件所使用，并通过应用程序框架为开发者提供服务
</br>&nbsp;&nbsp;&nbsp;&nbsp;Android运行时库：运行时库又分为核心库和ART(5.0系统之后，Dalvik虚拟机被ART取代)。核心库提供了Java语言核心库的大多数功能，这样开发者可以使用Java语言来编写Android应用。相较于JVM，Dalvik虚拟机是专门为移动设备定制的，允许在有限的内存中同时运行多个虚拟机的实例，并且每一个Dalvik 应用作为一个独立的Linux 进程执行。独立的进程可以防止在虚拟机崩溃的时候所有程序都被关闭。而替代Dalvik虚拟机的ART 的机制与Dalvik 不同。在Dalvik下，应用每次运行的时候，字节码都需要通过即时编译器转换为机器码，这会拖慢应用的运行效率，而在ART 环境中，应用在第一次安装的时候，字节码就会预先编译成机器码，使其成为真正的本地应用。

* **硬件抽象层（HAL)**
</br>硬件抽象层是位于操作系统内核与硬件电路之间的接口层，其目的在于将硬件抽象化，为了保护硬件厂商的知识产权，它隐藏了特定平台的硬件接口细节，为操作系统提供虚拟硬件平台，使其具有硬件无关性，可在多种平台上进行移植。 从软硬件测试的角度来看，软硬件的测试工作都可分别基于硬件抽象层来完成，使得软硬件测试工作的并行进行成为可能。通俗来讲，就是将控制硬件的动作放在硬件抽象层中。

* **Linux内核层**
</br>Android 的核心系统服务基于Linux 内核，在此基础上添加了部分Android专用的驱动。系统的安全性、内存管理、进程管理、网络协议栈和驱动模型等都依赖于该内核。 
</br>Android系统的五层架构就讲到这，了解以上的知识对以后分析系统源码有很大的帮助。

### &nbsp;&nbsp;&nbsp;&nbsp;1.2&nbsp;&nbsp;Android应用开发特色

* **四大组件**

</br>Android系统四大组件分别是活动(Activity) , 服务(Service) , 广播接收器(Broadcast Receiver) ,和内容提供器(Content Provider)。

1.*活动*是所有Android应用程序的门面,凡是在应用中你看得到的东西,都是放在活动中的。  就是用户交互?

2.*服务*,你无法看到,但它会一直在后台默默地运行,即使用户退出了应用,服务仍然是可以继续运行的。

3.*广播接收器*允许你的应用接收来自各处的广播消息,比如电话,短信等.当然你的应用也可以向外发出广播消息。

4.*内容提供器*则为应用程序之间共享数据提供了可能.比如你想要读取系统电话簿中的联系人,就需要通过内容提供器来实现。

* **丰富的系统控件**
</br>Android系统为开发者提供了丰富的系统控件,使得我们可以很轻松地编写出漂亮的界面,当然也可以定制属于自己的控件。

* **SQLite数据库**
</br>Android系统还自带了这种轻量级\运算速度极快的嵌入式关系型数据库.它不仅支持标准的SQL语法,还可以通过Android封装好的API进行操作,让存储和读取数据变得非常方便。

* **地理位置定位**
</br>移动设备与PC相比,地理位置定位功能是一个很大的亮点.现在的移动Android手机都内置有GPS,走到哪都可以定位到自己的位置,发挥你的想象就可以做出创意十足的应用。

* **强大的多媒体**
</br>Android系统还提供了丰富的多媒体服务,如音乐.视频.录音.拍照.闹铃等等,着一些你都可以在程序中通过代码进行控制,让你的应用变得更加丰富多彩。

* **传感器**
</br>Android手机中都会内置多种传感器,如加速度传感器,方向传感器等.这也算是移动设备的一大特点.通过灵活的使用这些传感器,你可以做出很多在PC上根本无法实现的应用。

### &nbsp;&nbsp;&nbsp;&nbsp;1.3&nbsp;&nbsp;跟我一起搭建开发环境
#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.3.1 准备所需要的工具
&nbsp;&nbsp;Android的程序都是通过Java来写的，如果你是对Java略有了解的话，就需要在学习Android的过程中补充一下Java知识了。那么，Android开发需要哪些工具呢？

<br>&nbsp;&nbsp;Δ **JDK**是Java语言的软件开发包，Android需要下载JDK8或以上的版本才行。
<br>&nbsp;&nbsp;Δ Android **SDK**是Android开发工具包，我们需要引入该包来使用相关api。
<br>&nbsp;&nbsp;Δ Android studio 的下载（它有什么优点呢？）
1. Google推出的，这个是它的最大优势，Android Stuido是Google推出，专门为Android“量身订做”的

2. 速度更快，Eclipse的启动速度、响应速度、内存占用一直被诟病

3. UI更漂亮，Stuido自带的Darcula主题的炫酷黑界面实在是高大上，相比而言Eclipse下的黑色主题太low了

4. 提示补全对于开发来说意义重大， Studio则更加智能，智能保存，从此再也不用每次都 Ctrl + S了。熟悉Studio以后效率会大大提升。

5. 整合了Gradle构建工具，Gradle是一个新的构建工具，自Studio亮相之处就支持Gradle，可以说Gradle集合了Ant和Maven的优点，不管是配置、编译、打包都非常棒。

6. 强大的UI编辑器，Android Studio的编辑器非常的智能，除了吸收Eclipse+ADT的优点之外，还自带了多设备的实时预览，相对这对Android开发者来说简直是神器啊。

7. 安装的时候就自带了如GitHub, Git, SVN等流行的版本控制系统，可以直接check out你的项目。

#### &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1.3.2 搭建开发环境
&nbsp;&nbsp;到Android官网就可以下载android studio了，地址是<http://developer.android.com/studio/index.html>，不过，一般需要科学上网才能访问它。如果你无法访问的话，就可以在<http://www.androiddevtools.cn/index.html>这里下载，然后安装就行了。注意，一定要根据自己的版本来下载Android studio。
</br>&nbsp;&nbsp;然后，就可以开始安装了

</br>![image](https://upload-images.jianshu.io/upload_images/13503052-423920825c2b8bc4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/623)
</br>![image](https://upload-images.jianshu.io/upload_images/13503052-579b17c1df1de46f.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/623)

</br>第一个是Android Studio主程序，必选。

</br>第二个是Android SDK，会安装Android5.0版本的SDK，也勾上。

</br>第三个和第四个是虚拟机和虚拟机的加速程序，如果你要在电脑上使用虚拟机调试程序，就勾上。

完成后点击next下一步。

</br>![image](https://upload-images.jianshu.io/upload_images/13503052-9bb86f64dbcfe312.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/623)
</br>![](https://upload-images.jianshu.io/upload_images/13503052-bee2d64e45e2af76.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/623)

</br>注意，这里可以自定义安装目录，但事实安装目录必须是全英文的

</br>![](https://upload-images.jianshu.io/upload_images/13503052-1926d9aeed14b112.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/623)
![](https://upload-images.jianshu.io/upload_images/13503052-48caa1e507e8589c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/623)
![](https://upload-images.jianshu.io/upload_images/13503052-95471523ccf9004a.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/623)

</br>打开Android studio后，进入相关配置

</br>![](https://upload-images.jianshu.io/upload_images/13503052-f17f7d4a3fe61dbc.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/699)

</br> 这是用于导入Android studio的配置文件，如果是第一次安装，选择最后一项：不导入配置文件，然后点击OK即可。

</br>上一步完成后，就会进入如下页面，这是程序在检查SDK的更新情况。

</br>![](https://upload-images.jianshu.io/upload_images/13503052-b611d98a4227a2c4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/500)

</br>第一次进入可能会出现以下界面，我们选择Setup Proxy进入下一步

</br>![](https://upload-images.jianshu.io/upload_images/13503052-f3040c4a68904514.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/383)

</br>![](https://upload-images.jianshu.io/upload_images/13503052-108e1a5142cd3cb6.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/504)

</br>下面选择默认配置即可点击Next

![](https://upload-images.jianshu.io/upload_images/13503052-9e73f818126097d8.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)
![](https://upload-images.jianshu.io/upload_images/13503052-0a72ff69fa2449d0.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)
![](https://upload-images.jianshu.io/upload_images/13503052-bd0ba3fc391cfb1a.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)
![](https://upload-images.jianshu.io/upload_images/13503052-496b8f1d74480286.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)
![](https://upload-images.jianshu.io/upload_images/13503052-8dcdebf9a8da2ea8.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

### 1.4&nbsp;&nbsp;创建第一个Android项目
&nbsp;&nbsp;我们先来创建一个Hello World项目吧
#### 1.4.1&nbsp;&nbsp;创建第一个Android项目
&nbsp;&nbsp;在Android studio欢迎界面点击start a new Android Studio project，如图:

![](https://upload-images.jianshu.io/upload_images/13503052-db79de1d45aca58c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

</br>输入你的项目名称“Hello World”.

“Company Domian”:这是公司域名，可以就填 example.com

“Project Location”：你应该新建一个目录，专名用来放android 项目的。就把这个projectLocation指向你的目录。

第二步，“Target Android Devices”，默认就是了。

第三步，我们就选择一个空的activity吧！

![](https://upload-images.jianshu.io/upload_images/13503052-d3f5621e372a77c1.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

第四步，“Custom The Activity”,默认就是了。点击“Finsh”。

点击完“Finsh”之后，不要着急，稍等几秒，android </br>studio对项目进行配置。会弹出这个。

![](https://upload-images.jianshu.io/upload_images/13503052-471281a8d05ee242.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/550)
![](https://upload-images.jianshu.io/upload_images/13503052-5289d25be4f1c7ae.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

![](https://upload-images.jianshu.io/upload_images/13503052-b5ab9e640ccd96b4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/73)
</br>选择运行/调试的配置

![](https://upload-images.jianshu.io/upload_images/13503052-acc2f7eaaeedafd0.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/22)
</br>运行项目

![](https://upload-images.jianshu.io/upload_images/13503052-6943359b6a528599.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/25)
</br>Gradle同步在你项目运行或者更改Gradle配置的时候都要点击下这个按钮，会下载相应的依赖

![](https://upload-images.jianshu.io/upload_images/13503052-3d46c4e4455491d1.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/29)
</br>AVD Manager模拟器管理

![](https://upload-images.jianshu.io/upload_images/13503052-1a5a83172c4bc103.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/25)
</br>SDK Manager就是管理你的SDK版本

![](https://upload-images.jianshu.io/upload_images/13503052-be3f2b66da11e5ac.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/27)
</br>DDMS即 Dalvik Debug Monitor Service，Dalvik调试监控服务。

运行项目有两种方式：

用自己的android手机运行（推荐）

用android emulator(安卓手机模拟器)，这个用起来有点卡，当然电脑配置很好的话就可以用模拟器

Δ手机调试：(手机需要调至开发者模式)
（1）将手机用USB连接电脑
（2）勾选“连接后启动调试模式”，不是仅能充电，而是可以传文件的那个选项
（3）点击运行android-studio-hello-word-05，弹出Device Dialog选择框，选择连接的设备，点击OK。

Δ模拟器需要下载：
<br>（1）点击”AVD Manager”按钮，出现“Android Virtual Device Manger”窗口，点击

![](https://upload-images.jianshu.io/upload_images/13503052-ceb321d080875444.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/199)

创建虚拟设备模拟器。

(2)选择设备，我就选择默认的Phone Nexus 5X。

![](https://upload-images.jianshu.io/upload_images/13503052-7a578ce18ef637e4.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

<br>(3)点击“Next，进入“Select Image”窗口界面，选择系统版本，一般默认选择最高版本的。（现在最高的是Android 6.0）
<br>(4)点击”Next”, 进入“AVD verify configuration”窗口界面，一般不修改的话，就是默认。注意手机尺寸Scale 一般是设置Auto,自动配置大小。点击“Finsh”。
<br>(5)稍等片刻，我们就看到模拟器创建出来了。

![](https://upload-images.jianshu.io/upload_images/13503052-6d78a536cf2ad36d.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/700)

(6)模拟器创建好了，我们就用模拟器运行项目吧！点击“Run App”弹出选择运行设备的窗口，我们看到了我们刚刚创建的模拟器“Nexus 5X API23”。

![](https://upload-images.jianshu.io/upload_images/13503052-9726d127be417c98.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/643)

再点ok就行了

![](https://upload-images.jianshu.io/upload_images/13503052-c6b8d86b27af1d23.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/344)

#### &nbsp;&nbsp;&nbsp;&nbsp;1.4.2&nbsp;&nbsp;分析Android的工程目录

![](https://upload-images.jianshu.io/upload_images/13503052-e7e9239dd839c9fa.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/392)

1、.gradle和.idea
        这两个目录下放置的都是Android Studio自动生成的一些文件，我们无须关心，也不要去手动编辑。
        
2、app
        项目中的代码、资源等内容几乎都是放置在这个目录下的，我们后面的开发工作也基本都是在这个目录下进行的，待会儿还会对这个目录单独展开进行讲解。
        
3、build
        这个目录你也不需要过多关心，它主要包含了一些在编译时自动生成的文件。
        
4、gradle
        这个目录下包含了gradle wrapper的配置文件，使用gradle wrapper的方式不需要提前将gradle下载好，而是会自动根据本地的缓存情况决定是否需要联网下载gradle。Android Studio默认没有启动gradle wrapper的方式，如果需要打开，可以点击Android Studio导航栏 --> File --> Settings --> Build，Execution，Deployment --> Gradle，进行配置更改。

5、.gitignore
        这个文件是用来将指定的目录或文件排除在版本控制之外的。

6、build.gradle
        这是项目全局的gradle构建脚本，通常这个文件中的内容是不需要修改的。下面会详细分析gradle构建脚本中的具体内容。

7、gradle.properties
        这个文件是全局的gradle配置文件，在这里配置的属性将会影响到项目中所有的gradle编译脚本。

8、gradlew和gradlew.bat
        这两个文件是用来在命令行界面中执行gradle命令的，其中gradlew是在Linux或Mac系统中使用的，gradlew.bat是在Windows系统中使用的。

9、HelloWorld.iml
        iml文件是所有IntelliJ IDEA项目都会自动生成的一个文件(Android Studio是基于IntelliJ IDEA开发的)，用于标识这是一个IntelliJ IDEA项目，我们不需要修改这个文件中的任何内容。

10、local.properties
        这个文件用于指定本机中的Android SDK路径，通常内容都是自动生成的，我们并不需要修改。除非你本机中的Android SDK位置发生了变化，那么就将这个文件中的路径改成新的位置即可。

11、settings.gradle
        这个文件用于指定项目中所有引入的模块。由于HelloWorld项目中就只有一个app模块，因此该文件中也就只引入了app这一个模块。通常情况下模块的引入都是自动完成的，需要我们手动去修改这个文件的场景可能比较少。

#### &nbsp;&nbsp;&nbsp;&nbsp;1.4.3&nbsp;&nbsp;Android的app目录
![](https://upload-images.jianshu.io/upload_images/13503052-918c8a2eb2d8b709.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/395)
 <br>那么下面我们就来对app目录下的内容进行更为详细的分析。

1、build
        这个目录和外层的build目录类似，主要也是包含了一些在编译时自动生成的文件，不过它里面的内容会更多更杂，我们不需要过多关系。

2、libs
        如果你的项目中使用到了第三方jar包，就需要把这些jar包都放在libs目录下，放在这个目录下的jar包都会被自动添加到构建路径里去。

3、AndroidTest
        此处是用来编写Android Test测试用例的，可以对项目进行一些自动化测试。

4、java
        毫无疑问，java目录是放置我们所有java代码的地方，展开该目录，你将看到我们刚才创建的HelloWorldActivity文件就在里面。

5、res
        这个目录下的内容就有点多了。简单点说，就是你在项目中使用到的所有图片，布局，字符串等资源都要存放在这个目录下。当然这个目录下还有很多子目录，图片放在drawable目录下，布局放在layout目录下，字符串放在values目录下，所以你不用担心会把整个res目录弄得乱糟糟的。

6、AndroidManifest.xml
        这是你整个Android项目的配置文件，你在程序中定义的所以四大组件都需要在这个文件里注册，另外还可以在这个文件中给应用程序添加权限声明。

7、test
        此处是用来编写Unit Test测试用例的，是对项目进行自动化测试的另一种方式。

8、.gitignore
        这个文件用于将app模块内的指定的目录或文件排除在版本控制之外，作用和外层的.gitignore文件类似。

9、app.iml
        IntelliJ IDEA项目自动生成的文件，我们不需要关心或修改这个文件中的内容。

10、build.gradle
        这是app模块的gradle构建脚本，这个文件中会指定很多项目构建相关的配置。

11、proguard-rules.pro
        这个文件用于指定项目代码的混淆规则，当代码开发完成后打成安装包文件，如果不希望代码被别人破解，通常会将代码混淆，从而让破解者难以阅读。
#### &nbsp;&nbsp;&nbsp;&nbsp;1.4.4&nbsp;&nbsp;Android项目中的资源
看到这么多的文件夹也不用害怕，其实归纳一下，res目录就变得非常简单了。

以drawable开头的文件夹都是用来放图片的，

以mipmap开头的文件夹都是用来放应用图标的，

以values开头的文件夹都是用来放字符串、样式、颜色等配置的，

layout文件夹是用来放布局文件的。
