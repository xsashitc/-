#### 一、准备工具

1. apktool

2. dex2jar

3. jd-gui

#### 二、工具下载

1. apktool

   [apktool下载地址](https://bitbucket.org/iBotPeaches/apktool/downloads/)

2. dex2jar

   [dex2jar下载地址](https://sourceforge.net/projects/dex2jar/files/)

3. jd-gui
[jd-gui下载地址](http://jd.benow.ca/)

#### 三、Apk反编译流程

1. 获取资源文件

   这一步用的是apktool工具，从网站上下载下来的是一个jar文件，jar文件使用的方法是在命令行中输入

   ```
   java -jar 文件名
   ```

   运行下列命令来使用apktool

   ```
   java -jar apktool-2.3.3.jar d -f apk位置 -o 位置
   ```

   最后的-o参数是可选的，将输出的文件存储到某一文件夹中

   在这个文件夹中我们可以看到所有的资源文件、AndroidMenifest文件等

   

2. 获取java源代码

   这一步需要用到dex2jar以及jd-gui

   首先将apk文件的后缀改为zip或rar，并将其解压

   在解压后的文件中，我们需要的是其中的classes.dex文件

   接下来输入如下命令运行dex2jar

   在mac os下：

   ```
   sh d2j-dex2jar.sh classes.dex
   ```

   在windows下：

   ```
   d2j-dex2jar classes.dex
   ```

   执行完成后我们得到classes-dex2jar.jar文件，在这个jar包中就包含了我们所需要的java源文件。接下来使用jd-gui查看源码，jd-gui下载下来是一个应用程序，直接打开并打开jar就可以查看了。
