Arduino资料下载
===============

**Arduino资料包含库文件、项目代码、驱动，请点击下载才能进行后续的学习！！！！**

下载：download:`Arduino资料 <./Arduino>`

Arduino IDE软件下载
===================

1、打开\ `Software \|
Arduino <https://www.arduino.cc/en/software>`__\ 下载软件，然后选择对应的系统下载，下面以window系统为例。(|image1|)

**注意：win11系统点击\ \ 此处进行到下载页面\ ,无需进行第2步操作.**

.. figure:: ./media/7ea915dd-dfa2-4b18-ae8a-853082fd85ad.png
   :alt: image-20250527121512549

   image-20250527121512549

2、然后选择”\ **只需下载**\ ”，再一次选择”\ **只需下载**\ ”，就可以看到正在下载的页面.

.. figure:: ./media/image-20250527115114993.png
   :alt: image-20250527115114993

   image-20250527115114993

Arduino IDE软件安装
===================

1、点击此处文件夹\ |image-20250527115344256|\ 进入到下载中心，双击\ |image-20250527115501137|\ 进行安装。

2、选择”\ **我同意(I)**\ ”，跳转页面后选择”\ **仅为我安装（Administrator)**\ ”,再点击”\ **下一步**\ ”。

.. figure:: ./media/image-20250527121512549-1748503184856-10.png
   :alt: image-20250527121512549

   image-20250527121512549

3、跳转页面后，点击”\ **浏览（B）**\ ”，可把软件放到指定位置（请用纯英文路径），点击”\ **安装**\ ”，安装完成后，点击”\ **完成**\ ”。

.. figure:: ./media/image-20250527122939211-1748503184856-9.png
   :alt: image-20250527122939211

   image-20250527122939211

**注：点击”完成“后，如果后面出现弹框，请选择肯定的回复，例如选择”是“、”安装“.**

Arduino驱动安装
===============

1、将主板连接到电脑

.. figure:: ./media/KE0171连接电脑-1748583924562-1.png
   :alt: KE0171连接电脑

   KE0171连接电脑

2、打开“设备管理器”.

.. figure:: ./media/image-20250527020321361-1748583924563-2.png
   :alt: image-20250527020321361

   image-20250527020321361

3、检查驱动是否已经安装

情况一：驱动安装完成，请跳过驱动教程，进行下一步学习

.. figure:: ./media/Snipaste_2025-05-30_10-25-37-1748583924563-3.png
   :alt: Snipaste_2025-05-30_10-25-37

   Snipaste_2025-05-30_10-25-37

情况二：驱动没有安装，请进行以下教程手动安装驱动

.. figure:: ./media/Snipaste_2025-05-30_11-27-48-1748583924563-8.png
   :alt: Snipaste_2025-05-30_11-27-48

   Snipaste_2025-05-30_11-27-48

1、鼠标右击\ **“USB串行设备”**\ ，在弹出框中选择\ **“更新驱动程序（P）”**

.. figure:: ./media/Snipaste_2025-05-30_11-31-19-1748583924563-4.png
   :alt: Snipaste_2025-05-30_11-31-19

   Snipaste_2025-05-30_11-31-19

2、点击选择\ **“浏览我的电脑以查找驱动程序（R）”**.

.. figure:: ./media/Snipaste_2025-05-30_11-34-54-1748583924563-9.png
   :alt: Snipaste_2025-05-30_11-34-54

   Snipaste_2025-05-30_11-34-54

3、点击\ **“浏览（R）“**\ 选项，在弹出的方框中选择提供的\ |Snipaste_2025-05-30_11-37-22|,点击\ **“确定”**\ ，完成后点击\ **“下一步”**\ 进行驱动安装.

**(记得下载驱动**

**image-20250530012313456)**

.. figure:: ./media/Snipaste_2025-05-30_11-47-46-1748583924563-6.png
   :alt: Snipaste_2025-05-30_11-47-46

   Snipaste_2025-05-30_11-47-46

4、界面显示如下图类似的话语，证明驱动安装成功，点击\ **“关闭“**.

.. figure:: ./media/Snipaste_2025-05-30_11-49-56-1748583924563-7.png
   :alt: Snipaste_2025-05-30_11-49-56

   Snipaste_2025-05-30_11-49-56

5.驱动安装完成后，选择\ **“端口”**\ 选项，如图对应端口的名字改变成Arduino
Uno，证明驱动安装完成.

.. figure:: ./media/Snipaste_2025-05-30_11-52-13-1748583924563-10.png
   :alt: Snipaste_2025-05-30_11-52-13

   Snipaste_2025-05-30_11-52-13

Arduino IDE的使用方法
=====================

Keyes UNO
R3开发板的USB驱动安装成功之后，我们可以在Windows设备管理器中找到相应的串口。

下面示范第一个程序的烧写，串口监视器中显示“Hello World！”。

测试代码为：

::

   int val;
   int ledpin=13; 

   void setup()
   {
       Serial.begin(9600);
       pinMode(ledpin,OUTPUT);
   }

   void loop()
   {
       val=Serial.read();
       if(val=='R')
       {
           digitalWrite(ledpin,HIGH);
           delay(500);
           digitalWrite(ledpin,LOW);
           delay(500);
           Serial.println("Hello World!");
       }
   }

我们打开Arduino 的软件，编写一段程序让Keyes UNO
R3开发板接受到我们发的指令就显示“Hello
World！”字符串；我们再借用一下Keyes UNO R3 开发板上的
D13的指示灯，让Keyes UNO
R3开发板接受到指令时指示灯闪烁一下，再显示“Hello World！”。

打开Arduino 的软件，设置板，如下。

.. figure:: ./media/image-20250529233818712.png
   :alt: image-20250529233818712

   image-20250529233818712

设置COM端口，如下

.. figure:: ./media/image-20250529233938665.png
   :alt: image-20250529233938665

   image-20250529233938665

点击\ |image2|\ 编译程序，检查程序是否错误；点击\ |image3|\ 上传程序；Keyes
UNO R3 开发板设置OK后右下脚显示如下图，和设备管理器中显示一致。

.. figure:: ./media/image-20250529234135452.png
   :alt: image-20250529234135452

   image-20250529234135452

上传成功，输入R，点击发送，Keyes UNO R3 开发板上的
D13的指示灯闪烁一次，串口监视器中显示 Hello World! 如下图

.. figure:: ./media/image-20250529234700578.png
   :alt: image-20250529234700578

   image-20250529234700578

那么恭喜你，你的第一个程序已经成功了！！！

项目课程
========

项目一 LED模块
--------------

实验说明

本实验我们主要用来检测LED模块。实验中我们将LED模块的信号端接在开发板数字口3上，它同时也是PWM口。我们用两个实验检测，一个是让LED进行闪烁实验;另一个是让PWM口控制LED的亮度，让LED逐渐变亮和逐渐变暗，模拟人体呼吸的现象。

实验器材

开发板*1

USB线*1

LED模块*1

（草帽LED模块、食人鱼LED模块和3W LED模块都可以）

杜邦线若干

|image4|

测试代码

代码A:

::

   int led = 3; //定义数字口3

   void setup()
   {
       pinMode(led, OUTPUT);//设置led为输出
   }

   void loop()
   {
       digitalWrite(led, HIGH);//开启led
       delay(1000); //延迟1秒
       digitalWrite(led, LOW);//关闭led
       delay(1000);//延迟1秒
   }

代码B:

::

   int ledPin = 3; // 定义数字口3

   void setup()
   {
       pinMode(ledPin, OUTPUT);// 将ledPin设置为输出
   }

   void loop()
   {
       for (int a=0; a<=255;a++)// 设置使LED逐渐变亮
       {
           analogWrite(ledPin,a); //开启led,调节亮度，范围是0-255，在255时led最亮
           delay(10); // 延迟0.01秒
       }
       for (int a=255; a>=0;a--) // 设置使LED逐渐变暗
       {
           analogWrite(ledPin,a); //开启led,调节亮度，范围是0-255，在255时led最亮
           delay(10); // 延迟0.01秒
       }
       delay(1000);// 延迟1秒
   }

测试结果

上传完代码A，上电后，我们就可以看到LED不停闪烁，间隔大约为1秒。上传完代码B，上电后，我们就可以看到LED先逐渐变亮，后逐渐变暗，循环交替。

项目二 干簧管模块
-----------------

实验说明

本实验我们主要用来检测干簧管模块。该模块主要由干簧管组成，模块接上电源后，信号端输出为高电平，传感器上LED变暗；当给模块施加一个磁场时信号端输出为低电平，传感器上LED变亮。实验中我们用到了Arduino
UNO 板上自带的D13 的指示灯，通过传感器，控制D13 的指示灯的亮灭。

实验器材

开发板*1

USB线*1

干簧管模块*1

杜邦线若干

接线图

|image5|

测试代码

::

   int Led=13;//定义数字口13
   int buttonpin=3; //定义数字口3
   int val;//定义数字变量val

   void setup()
   {
       pinMode(Led,OUTPUT);//将Led设置为输出
       pinMode(buttonpin,INPUT);//将buttonpin设置为输入
   }

   void loop()
   {
       val=digitalRead(buttonpin);// 读取数字口3的数值，并赋值给val
       if(val==LOW)//当val为高电平时
       {
           digitalWrite(Led,HIGH); //LED亮起
       }
       else
       {
           digitalWrite(Led,LOW); //LED熄灭
       }
   }

测试结果

按照上图接好线，上传好代码，上电后，Arduino UNO 板上的
D13的指示灯熄灭，模块上D1灯熄灭；当有磁铁靠近模块时， Arduino UNO
板上的D13 的指示灯亮起，模块上D1灯亮。

项目三 有源蜂鸣器模块
---------------------

实验说明

本实验我们主要用来检测有源蜂鸣器模块。它主要由有源蜂鸣器组成，是一种一体化结构的电子讯响器，采用直流电源供电。模块接上电源后，当我们直接给信号端输入个高电平信号后，蜂鸣器响起。实验中我们让有源蜂鸣器模块循环响起，关闭。

实验器材

开发板*1

USB线*1

有源蜂鸣器模块*1

杜邦线若干

接线图

|image6|

测试代码

::

   int buzzPin = 3;//定义数字口3

   void setup()
   {
     pinMode(buzzPin, OUTPUT);//将buzzPin设置为输出
   }

   void loop()
   {
     digitalWrite(buzzPin, HIGH);//有源蜂鸣器响起
     delay(2000); //延迟2秒
     digitalWrite(buzzPin, LOW); //有源蜂鸣器关闭
     delay(2000);//延迟2秒     
   }

测试结果

有源蜂鸣器只需要有个高电平电压蜂鸣器就响起。上传好代码，连接好线，上电后，有源蜂鸣器响2秒，静音2秒，循环交替。

项目四 无源蜂鸣器模块
---------------------

实验说明

本实验我们主要用来检测草无源蜂鸣器模块。蜂鸣器可分为有源蜂鸣器和无源蜂鸣器两种。无源蜂鸣器内部不带振荡源，直流信号无法令其鸣叫，须用方波驱动。

实验中我们将无源蜂鸣器模块的信号端接在开发板的数字口3上，通过开发板控制数字口3输出方波，从而驱动无源蜂鸣器。我们用两个实验检测，一个是让数字口3循环输出两种频率的方波，驱动无源蜂鸣器响起;另一个是我们让数字口3输出各种频率的方波，并且设定好节奏，从而让无源蜂鸣器播放《欢乐颂》的曲子。

实验器材

开发板*1

USB线*1

无源蜂鸣器模块*1

杜邦线若干

接线图

|image7|

测试代码

代码A:

::

   int buzzer=3; //定义数字口3

   void setup()
   {
       pinMode(buzzer,OUTPUT);//将buzzer设置为输出
   }

   void loop()
   {
       unsigned char i,j;//定义变量i，j
       while(1)
       {
           for(i=0;i<80;i++)// 输出一个频率的声音
           {
               digitalWrite(buzzer,HIGH);
               delay(1);//延迟1ms
               digitalWrite(buzzer,LOW);
               delay(1);//延迟1ms
           }
           for(i=0;i<100;i++)// 输出另一个频率的声音
           {
               digitalWrite(buzzer,HIGH);
               delay(2);//延迟2ms
               digitalWrite(buzzer,LOW);
               delay(2);//延迟2ms
           }
       }
   }

代码B:

::

   #define D0 -1
   #define D1 262
   #define D2 293
   #define D3 329
   #define D4 349
   #define D5 392
   #define D6 440
   #define D7 494
   #define M1 523
   #define M2 586
   #define M3 658
   #define M4 697
   #define M5 783
   #define M6 879
   #define M7 987
   #define H1 1045
   #define H2 1171
   #define H3 1316
   #define H4 1393
   #define H5 1563
   #define H6 1755
   #define H7 1971

   //列出全部D调的频率
   #define WHOLE 1
   #define HALF 0.5
   #define QUARTER 0.25
   #define EIGHTH 0.25
   #define SIXTEENTH 0.625
   //列出所有节拍

   int tune[]= //根据简谱列出各频率
   {
       M3,M3,M4,M5,
       M5,M4,M3,M2,
       M1,M1,M2,M3,
       M3,M2,M2,
       M3,M3,M4,M5,
       M5,M4,M3,M2,
       M1,M1,M2,M3,
       M2,M1,M1,
       M2,M2,M3,M1,
       M2,M3,M4,M3,M1,
       M2,M3,M4,M3,M2,
       M1,M2,D5,D0,
       M3,M3,M4,M5,
       M5,M4,M3,M4,M2,
       M1,M1,M2,M3,
       M2,M1,M1
   };

   float durt[]= //根据简谱列出各节拍
   {
       1,1,1,1,
       1,1,1,1,
       1,1,1,1,
       1+0.5,0.5,1+1,
       1,1,1,1,
       1,1,1,1,
       1,1,1,1,
       1+0.5,0.5,1+1,
       1,1,1,1,
       1,0.5,0.5,1,1,
       1,0.5,0.5,1,1,
       1,1,1,1,
       1,1,1,1,
       1,1,1,0.5,0.5,
       1,1,1,1,
       1+0.5,0.5,1+1,
   };

   int length;
   int tonepin=3; //得用3号接口

   void setup()
   {
       pinMode(tonepin,OUTPUT);
       length=sizeof(tune)/sizeof(tune[0]); //计算长度
   }

   void loop()
   {
       for(int x=0;x<length;x++)
       {
           tone(tonepin,tune[x]);
           delay(500*durt[x]);
           //这里用来根据节拍调节延时，500这个指数可以自己调整，在该音乐中，我发现用500比较合适。
           noTone(tonepin);
       }
       delay(2000);
   }

测试结果

上传完代码A，上电后，无源蜂鸣器会发出两种不同的声音，两种声音循环交替。上传完代码B，上电后，无源蜂鸣器会想响起《欢乐颂》的曲子。

项目五 旋转编码器模块
---------------------

实验说明

本实验我们主要用来检测旋转编码器模块。它主要由旋转编码器组成，它可通过旋转可以计数正方向和反方向转动过程中输出脉冲的次数，这种转动计数是没有限制的，复位到初始状态，即从0开始计数。实验中我们利用一个旋转编码器模块控制两个草帽LED的亮灭。

实验器材

开发板*1

USB线*1

旋转编码器模块*1

LED模块*2

杜邦线若干

接线图

|image8|

测试代码

::

   const int interruptA = 0; //中断0就是在数字口2
   const int interruptB = 1;//中断1就是在数字口3

   int CLK = 2; // 定义数字口2
   int DAT = 3; // 定义数字口3
   int BUTTON = 4; // 定义数字口4
   int LED1 = 5; // 定义数字口5
   int LED2 = 6; // 定义数字口6
   int COUNT = 0;//设置数字变量COUNT为0

   void setup()
   {
       attachInterrupt(interruptA, RoteStateChanged, FALLING); // 当数字口2由高电平变为低电平时，触发中断。
       pinMode(CLK, INPUT);//设置CLK为输入
       digitalWrite(2, HIGH); // 设置数字口2为高电平
       pinMode(DAT, INPUT); //设置DAT为输入
       digitalWrite(3, HIGH); //设置数字口3为高电平
       pinMode(BUTTON, INPUT); //设置BUTTON为输入
       digitalWrite(4, HIGH); //设置数字口4为高电平
       pinMode(LED1, OUTPUT);//设置LED1为输出
       pinMode(LED2, OUTPUT);//设置LED1为输出
       Serial.begin(9600); //设置波特率
   }

   void loop()
   {
       if (digitalRead(BUTTON)==LOW)//当数字口4为低电平时
       {
           COUNT = 0; //设置数字变量COUNT为0
           Serial.println("STOP COUNT = 0");//显示对于内容
           digitalWrite(LED1, LOW);//LED1变暗
           digitalWrite(LED2, LOW);//LED2变暗
           delay (2000);//延迟2S
       }
       Serial.println(COUNT);//显示COUNT数据
   }

   void RoteStateChanged() //当数字口2由高电平变为低电平时
   {
       if (digitalRead(DAT)==HIGH) // 当数字口3为高电平时
       {
           COUNT++;//数字变量COUNT加1
           digitalWrite(LED1, HIGH);//LED1亮起
           digitalWrite(LED2, LOW);//LED2变暗
           delay(200);//延迟0.2S
       }
       else
       {
           COUNT--;//数字变量COUNT减1
           digitalWrite(LED2, HIGH);//LED2亮起
           digitalWrite(LED1, LOW);//LED1变暗
           delay(200);//延迟0.2S
       }
   }

测试结果

上传好代码，连接好线，上电后，我们可以通过旋转旋转编码器，可以随意控制两个草帽LED的亮灭。

项目六 可调电位器模块
---------------------

实验说明

本实验我们主要用来检测可调电位器模块。它主要由可调电位器组成，模块上电后，我们只需旋转模块上电位器就可以调节模拟输入数值。实验中将模块的S端接到开发板的模拟口A0，在Arduino
IDE的串口监视器上可看到对应的模拟值显示。

实验器材

开发板*1

USB线*1

可调电位器模块*1

杜邦线若干

接线图

|image9|

测试代码

::

   int sensorPin =A0 ; //定义模拟口A0
   int value = 0; //设置value为0

   void setup()
   {
       Serial.begin(9600);//设置波特率
   }

   void loop()
   {
       value = analogRead(sensorPin); //将value设置为读取到的A0的数值
       Serial.println(value, DEC); //显示value数值，并自动换行
       delay(100); //延迟0.1秒
   }

测试结果

按照上图接好线，烧录好代码，上电后，我们可以在软件的串口监视器中看到模拟口A0模拟值，旋转旋钮，数据变化，变化范围在0-1023，如下图。

项目七 5V单路继电器模块
-----------------------

实验说明

本实验我们主要用来检测5V单路继电器模块。这个继电器模块是高电平有效，我们把继电器模块的信号端接在数字口3。实验中我们通过开发板控制数字口3，控制模块上继电器循环开启和关闭。

实验器材

开发板*1

USB线*1

5V 单路继电器模块*1

杜邦线若干

接线图

|image10|

测试代码

::

   int Relay = 3; //定义数字口3

   void setup()
   {
       pinMode(Relay, OUTPUT); //将Relay设置为输出
   }

   void loop()
   {
       digitalWrite(Relay, HIGH); //打开继电器
       delay(2000); //延时2秒
       digitalWrite(Relay, LOW); //关闭继电器
       delay(2000); //延时2秒
   }

测试结果

按照上图接好线，上传好代码，上电后，继电器开启（ON端连通，NC断开）2秒，停止（ON端断开，NC端连通）2秒，循环交替，开启时继电器上D2灯亮起。

项目八 插件RGB模块
------------------

实验说明

本实验我们主要用来检测插件RGB模块。本模块由主要一个插件全彩LED制成，通过R、
G、B三个引脚的PWM电压输入可以调节三种基色（红/蓝/绿）的强度从而实现全彩的混色效果。我们用Arduino对模块的控制可实现酷炫的灯光效果。实验中我们让插件RGB模块循环显示不同颜色。

实验器材

开发板*1

USB线*1

插件RGB模块*1

杜邦线若干

接线图

|image11|

测试代码

::

   int redPin = 6;   // 红色LED控制引脚，连接到Arduino的6脚
   int greenPin = 5; // 绿色LED控制引脚，连接到Arduino的5脚
   int bluePin = 3;  // 蓝色LED控制引脚，连接到Arduino的3脚

   void setup()
   {
       pinMode(redPin, OUTPUT);   // 设置redPin对应的管脚6为输出模式
       pinMode(greenPin, OUTPUT); // 设置greenPin对应的管脚5为输出模式
       pinMode(bluePin, OUTPUT);  // 设置bluePin对应的管脚3为输出模式
   }

   void loop() 
   {
       // 基本颜色:
       color(255, 0, 0);    // 红色亮
       delay(1000);         // 延时一秒
       
       color(0, 255, 0);    // 绿色亮
       delay(1000);         // 延时一秒
       
       color(0, 0, 255);    // 蓝色亮
       delay(1000);         // 延时一秒
       
       // 混合颜色示例:
       color(255, 255, 0);  // 黄色亮
       delay(1000);         // 延时一秒
       
       color(128, 0, 255); // 紫色亮
       delay(1000);         // 延时一秒
       
       color(255, 255, 255); // 白色亮
       delay(1000);          // 延时一秒
       
       color(0, 0, 0);      // 关闭LED
       delay(1000);         // 延时一秒
   }

   void color(unsigned char red, unsigned char green, unsigned char blue) // 颜色控制函数
   {
       analogWrite(redPin, red);
       analogWrite(greenPin, green);
       analogWrite(bluePin, blue);
   }

测试结果

上传完代码，上电后，RGB模块会陆续显示红色1秒，绿色1秒，蓝色1秒，黄色1秒，紫色1秒，白色1秒，停止显示1秒，然后循环交替。

项目九 热敏电阻传感器
---------------------

实验说明

本实验我们主要用来检测热敏电阻传感器。它是基于热敏电阻的工作原理，能够实时感知周边环境温度的变化，我们把数据送到Arduino的模拟口，接来下我们只要经过简单的编程就能将传感器输出的数据转换为摄氏温度值，并加以显示，借此广泛应用于园艺、家庭警报系统等装置中。

实验中将传感器的信号端接到开发板的模拟口A0，在Arduino
IDE的串口监视器上可看到当前环境中的温度值。

实验器材

开发板*1

USB线*1

热敏电阻传感器*1

杜邦线若干

接线图

|image12|

测试代码

::

   #include <math.h>

   double Thermister(int RawADC) 
   {
       double Temp;
       Temp = log(((10240000 / RawADC) - 10000));
       Temp = 1 / (0.001129148 + (0.000234125 + (0.0000000876741 * Temp * Temp)) * Temp);
       Temp = Temp - 273.15;  // 将开尔文温度转换为摄氏度
       return Temp;
   }

   void setup() 
   {
       Serial.begin(9600);  // 设置串口波特率为9600
   }

   void loop() 
   {
       Serial.print(Thermister(analogRead(A0)));  // 读取并显示计算得到的温度值
       Serial.println("c");                      // 显示单位"c"并自动换行
       delay(500);                               // 延迟500毫秒(0.5秒)
   }

测试结果

按照上图接好线，上传好代码，上电后，我们可以在软件的串口监视器中看到当前环境中的温度值，如下图。

项目十 按键传感器
-----------------

实验说明

本实验我们主要用来检测按键传感器。当我们按下按键时传感器信号端输出低电平信号，释放按键时传感器信号端保持高电平。实验中我们用到了Arduino
UNO 板上自带的D13 的指示灯，通过传感器，控制D13 的指示灯的亮灭。

实验器材

开发板*1

USB线*1

按键传感器*1

杜邦线若干

接线图

|image13|

测试代码

::

   int ledPin = 13; //定义数字口13
   int inputPin = 3; //定义数字口3

   void setup()
   {
       pinMode(ledPin, OUTPUT); //将ledPin设置为输出
       pinMode(inputPin, INPUT); //将inputPin设置为输入
   }

   void loop()
   {
       int val = digitalRead(inputPin);//设置数字变量val，读取到数字口3的数值，并赋值给 val
       if (val == LOW) //当val为低电平时，LED亮起
       {
           digitalWrite(ledPin, HIGH); // LED亮起
       }
       else
       {
           digitalWrite(ledPin, LOW); // LED变暗
       }
   }

测试结果

按照上图接好线，上传好代码，上电后，按下传感器按键后， Arduino UNO板上的
D13 的指示灯亮起，释放传感器按键后， Arduino UNO 板上的
D13的指示灯熄灭。

项目十一 DHT11温湿度传感器
--------------------------

实验说明

本实验我们主要用来检测DHT11温湿度传感器。它是一款含有已校准数字信号输出的温湿度复合传感器，它应用专用的数字模块采集技术和温湿度传感技术，确保产品具有极高的可靠性和卓越的长期稳定性。

实验中将传感器的信号端接到开发板的数字口3，在Arduino
IDE的串口监视器上可看到当前环境中的温度值和湿度值。

实验器材

开发板*1

USB线*1

DHT11温湿度传感器*1

杜邦线若干

接线图

|image14|

测试代码

::

   #include <DHT11.h>
   DHT11 dht11(3);//DHT11接在D3引脚

   void setup() 
   {
       Serial.begin(9600); 
   }

   void loop() 
   {
       int temperature = 0;
       int humidity = 0;
       int result=dht11.readTemperatureHumidity(temperature, humidity);
       if (result == 0) 
       {
           Serial.print("DHT11, OK");
           Serial.print("  温度: ");
           Serial.print(temperature);
           Serial.print(" C\t湿度: ");
           Serial.print(humidity);
           Serial.println(" %");
       } 
       else 
       {  
           Serial.println(DHT11::getErrorString(result));// 读取失败，打印错误信息
       }
   }

测试结果

按照上图接好线，上传好代码，上电后，我们可在软件串口监视器中看到当前环境中的温度值和湿度值，如下图。

项目十二 光敏电阻传感器
-----------------------

实验说明

本实验我们主要用来检测光敏电阻传感器。这个传感器对环境光线最敏感，一般用来检测周围环境的光线的亮度，触发单片机或继电器模块等。实验中将传感器的信号端接到开发板的模拟口A0，在Arduino
IDE的串口监视器上可看到对应的模拟值输出。

实验器材

开发板*1

USB线*1

光敏电阻传感器*1

杜邦线若干

接线图

|image15|

测试代码

::

   int sensorPin =A0 ; //定义模拟口A0
   int value = 0; //设置value为0

   void setup()
   {
         Serial.begin(9600); //设置波特率
   }

   void loop()
   {
       value = analogRead(sensorPin); //将value设置为读取到的A0的数值
       Serial.println(value, DEC); //显示value数值，并自动换行
       delay(200); //延迟0.2秒
   }

测试结果

按照上图接好线，上传好代码，上电后，我们可以在软件的串口监视器中看到代表当前光线强弱的模拟值，光线越强，数值越大，如下图。

项目十三 倾斜模块传感器
-----------------------

实验说明

本实验我们主要用来检测倾斜模块传感器。这个传感器主要是利用滚珠在开关内随不同倾斜角度的发化，达到触发电路的目的；可用于倾斜检测、报警器制作或者其他检测。实验中我们用到了Arduino
UNO 板上自带的D13 的指示灯，通过传感器，控制D13 的指示灯的亮灭。

实验器材

开发板*1

USB线*1

倾斜模块传感器*1

杜邦线若干

接线图

|image16|

测试代码

::

   int ledPin = 13; //定义数字口13
   int switcher = 3; // 定义数字口3

   void setup()
   {
       pinMode(ledPin, OUTPUT); // 将ledPin设置为输出
       pinMode(switcher, INPUT); //将switcher设置为输入
   }

   void loop()
   {
       if(digitalRead(switcher)==HIGH) //当读取数字口3，并发现为高电平
       {
           digitalWrite(ledPin, HIGH); // LED亮起
       }
       else
       {
           digitalWrite(ledPin, LOW); // LED变暗
       }
   }

测试结果

按照上图接好线，上传好代码，上电后，倾斜一方时 Arduino UNO 板上的
D13的指示灯亮，数字倾斜模块上D1灯灭；倾斜另一方时 Arduino UNO 板上的
D13的指示灯灭，数字倾斜模块上D1灯亮。

项目十四 麦克风声音传感器
-------------------------

实验说明

本实验我们主要用来检测麦克风声音传感器。这个传感器的S端是模拟输出，是麦克风的电压信号实时输出，通过电位器可调节信号增益。实验中将传感器的S端接到开发板的模拟口A0，在Arduino
IDE的串口监视器上可看到对应的模拟值输出。

实验器材

开发板*1

USB线*1

麦克风声音传感器*1

杜邦线若干

接线图

|image17|

测试代码

::

   int sensorPin =A0 ; //定义模拟口A0
   int value = 0; //设置value为0

   void setup()
   {
         Serial.begin(9600); //设置波特率
   }

   void loop()
   {
       value = analogRead(sensorPin); //将value设置为读取到的A0的数值
       Serial.println(value, DEC); //显示value数值，并自动换行
       delay(100); //延迟0.1秒
   }

测试结果

按照上图接好线，上传好代码，上电后，我们可以在软件的串口监视器相对应模拟值，如下图。声音越大模拟值越大。

项目十五 霍尔传感器
-------------------

实验说明

本实验我们主要用来检测霍尔传感器。传感器输入为磁感应强度，输出是一个数字电压信号。它具有体积小、灵敏度高、响应速度快、温度性能好、可靠性高等特点。产品可用于无触点开关、位置转速检测与控制、全报警装置、纺织控制系统等方面。实验中我们用到了Arduino
UNO 板上自带的D13 的指示灯，通过传感器，控制D13 的指示灯的亮灭。

实验器材

开发板*1

USB线*1

霍尔传感器*1

杜邦线若干

接线图

|image18|

测试代码

::

   int ledPin = 13; //定义数字口13
   int inputPin = 3; //定义数字口3
   int val = 0; //定义数字变量val，并设为0

   void setup()
   {
       pinMode(ledPin, OUTPUT); //将ledPin设置为输出
       pinMode(inputPin, INPUT); //将inputPin设置为输入
   }

   void loop()
   {
       val = digitalRead(inputPin); //读取到数字口3的数值，并赋值给val
       if (val == LOW) //当val为低电平时，LED亮起
       {
           digitalWrite(ledPin, HIGH); //LED亮起
       }
       else
       {
           digitalWrite(ledPin, LOW); //LED变暗
       }
   }

测试结果

按照上图接好线，上传好代码后，上电后，Arduino UNO 板上的
D13的指示灯关闭，模块上D1灯关闭；当有磁铁靠近模块时， Arduino UNO
板上的D13 的指示灯亮起，模块上D1灯亮起。

项目十六 碰撞传感器
-------------------

实验说明

本实验我们主要用来检测碰撞传感器。当传感器因碰撞物体按下按键时传感器信号端输出低电平信号，释放按键时传感器信号端保持高电平。该传感器可用于3D打印机内做限位开关。实验中我们用到了Arduino
UNO 板上自带的D13 的指示灯，通过传感器，控制D13 的指示灯的亮灭。

实验器材

开发板*1

USB线*1

碰撞传感器*1

杜邦线若干

接线图

|image19|

测试代码

::

   int Led=13;//定义 LED 接口
   int Shock=3;//定义碰撞传感器接口
   int val;//定义数字变量 val

   void setup()
   {
       pinMode(Led,OUTPUT);//定义 LED 为输出接口
       pinMode(Shock,INPUT);//定义碰撞击传感器为输出接口
   }

   void loop()
   {
       val=digitalRead(Shock);//将数字接口 3 的值读取赋给 val
       if(val==LOW)//当碰撞传感器检测有信号时，LED 亮起
       {
           digitalWrite(Led,HIGH); //LED 亮起
       }
       else
       {
           digitalWrite(Led,LOW); //LED 变暗
       }
   }

测试结果

按照上图接好线，烧录好代码；上电后，将碰撞传感器的小铁片往下压，Arduino
UNO 板上的 D13 的指示灯亮起和碰撞模块上D1灯亮起，否则。Arduino UNO
板上的 D13 的指示灯熄灭和碰撞模块上D1灯熄灭。

项目十七 敲击模块传感器
-----------------------

实验说明

本实验我们主要用来检测敲击模块传感器。它主要由SW-280振动开关组成，是电感式接近开关，是在感应震动力大小将感应结果传递到电路装置,并使电路启动工作的电子开关。实验中我们用到了Arduino
UNO 板上自带的D13 的指示灯，通过传感器，控制D13 的指示灯的亮灭。

实验器材

开发板*1

USB线*1

敲击模块传感器*1

杜邦线若干

接线图

|image20|

测试代码

::

   int Led=13;//定义数字口13
   int Shock=3;//定义数字口3
   int val;//定义数字变量val

   void setup()
   {
       pinMode(Led,OUTPUT);//将Led设置为输出
       pinMode(Shock,INPUT);//将Shock设置为输入
   }

   void loop()
   {
       val=digitalRead(Shock);//读取到数字口3的数值，并赋值给val
       if(val==LOW) //当val为低电平时，Led亮起
       {
           digitalWrite(Led,HIGH); //Led亮起
       }
       else
       {
           digitalWrite(Led,LOW); //Led变暗
       }
   }

测试结果

按照上图接好线，上传好代码，上电后，敲击该模块，Arduino UNO 板上的D13 的
LED 指示灯和模块上 D1 灯亮起。

项目十八 避障传感器
-------------------

实验说明

本实验我们主要用来检测避障传感器。接好线上电后，传感器感应到物体时信号端S输出0，未感应到时信号端S输出1。它可通过调节电位器用来调节感应灵敏度。它速度快，适合智能小车避障、黑白线循迹、防跌落，产品计数器，流水线切割，液位检测等。实验中我们用到了Arduino
UNO 板上自带的D13 的指示灯，通过传感器，控制D13 的指示灯的亮灭。

实验器材

开发板*1

USB线*1

避障传感器*1

杜邦线若干

接线图

|image21|

测试代码

::

   const int sensorPin = 3; //定义数字口13
   const int ledPin = 13; //定义数字口3
   int sensorState = 0; //定义数字变量sensorState，并设为0

   void setup()
   {
       pinMode(ledPin, OUTPUT); //将ledPin设置为输出
       pinMode(sensorPin, INPUT);//将sensorPin设置为输入
   }

   void loop()
   {
       sensorState = digitalRead(sensorPin);//读取到数字口3的数值，并赋值给sensorState
       if (sensorState == LOW) //当sensorState为低电平时，LED亮起
       {
           digitalWrite(ledPin, HIGH);//LED亮起
       }
       else
       {
           digitalWrite(ledPin, LOW);//LED变暗
       }
   }

测试结果

按照上图接好线，上传好代码，上电后，通电后，靠近红外发射头的电位器顺时针调到尽头，再调节靠近红外接收头的电位器，观察D1灯，使D1灯关闭，并且保持将要亮起的临界点，此时感应距离最长。没有障碍物挡住红外避障传感器时，红外避障传感器上的D1灯关闭，Arduino
UNO 板上的
D13的指示灯关闭；当用障碍物挡住红外避障传感器，红外避障传感器上的D1灯亮起，Arduino
UNO 板上的 D13 的指示灯亮起。

项目十九 LM35温度传感器
-----------------------

实验说明

本实验我们主要用来检测LM35温度传感器。它的输出电压与摄氏温标呈线性关系，转换公式如式，0时输出为0V，每升高1℃，输出电压增加10mV。

实验中将传感器的信号端接到开发板的模拟口A0，在Arduino
IDE的串口监视器上可看到当前环境中的温度值。

实验器材

开发板*1

USB线*1

LM35温度传感器*1

杜邦线若干

接线图

|image22|

测试代码

::

   void setup()
   {
       Serial.begin(9600);//设置波特率
   }

   void loop()
   {
       int val; //定义数字变量val
       int dat;//定义数字变量dat
       val=analogRead(A0);//将val设置为读取到的A0的数值
       dat=(500 * val) /1024; //计算出当前温度数字dat
       Serial.print("Temp:"); //显示 Temp:
       Serial.print(dat); //显示计算的温度值
       Serial.println("C");//显示C，并自动换行
       delay(500); //延迟0.5S
   }

测试结果

按照上图接好线，上传好代码，上电后，我们可以在软件的串口监视器中看到当前环境中的温度值，如下图。

项目二十 激光头传感器模块
-------------------------

实验说明

本实验我们主要用来检测激光头传感器模块。它主要由激光头组成，激光头由发光管芯、聚光透镜、铜可调套筒三部分组成。接上电源后，我们在信号端直接输入个高电平数字信号，传感器开始工作。它可用于激光类玩具、电子教鞭笔、电子水平尺、微型液晶投影等地方。实验中我们让激光头传感器模块循环开启，关闭。

实验器材

开发板*1

USB线*1

激光头传感器模块*1

杜邦线若干

接线图

|image23|

测试代码

::

   void setup()
   {
       pinMode(3, OUTPUT); // 定义3脚为数字输出接口
   }

   void loop() 
   {
       digitalWrite(3, HIGH); // 打开激光头
       delay(1000); // 延时一秒
       digitalWrite(3, LOW); // 关闭激光头
       delay(1000); // 延时一秒
   }

测试结果

按照上图接好线，上传好代码，上电后，激光头打开1秒，关闭1秒，循环交替。

项目二十一 巡线传感器
---------------------

实验说明

本实验我们主要用来检测巡线传感器。传感器上的TCRT5000红外对管的工作原理是利用红外线对颜色的反射率不一样，将反射信号的强弱转化成电流信号。传感器在检测到黑色高电平有效，检测到白色是为低电平有效，检测高度为0—3cm。在电路中你可以使用旋钮电位器来调黑白寻迹的灵敏度。

实验中将传感器的S端接到开发板的数字口D3，在Arduino
IDE的串口监视器上可看到对应的数值输出。

实验器材

开发板*1

USB线*1

巡线传感器*1

杜邦线若干

接线图

|image24|

测试代码

::

   void setup()
   {
       Serial.begin(9600);//设置波特率
   }

   void loop()
   {
       Serial.println(digitalRead(3)); //输出从数字口3读取到的数值，并自动换行
       delay(500);//延迟0.5秒
   }

测试结果

按照上图接好线，上传好代码，上电后，传感器在检测到黑色时，信号端输出高电平，串口监视器显示1，传感器上D1指示灯熄灭；传感器在检测到其他颜色时，信号端输出低电平，串口监视器显示0，传感器上D1指示灯亮起。旋转电位器可调节灵敏度，将D1调节至亮与不亮的临界点时，灵敏度最高。

项目二十二 18B20温度传感器
--------------------------

实验说明

本实验我们主要用来检测18B20温度传感器。该传感器主要由DS18B20可编程数字温度器等组成，具有体积小，抗干扰能力强，精度高的特点。它的测温范围
－55℃～+125℃，固有测温误差是1℃。

实验中将传感器的信号端接到开发板的数字口3，在Arduino
IDE的串口监视器上可看到当前环境中的温度值。

实验器材

开发板*1

USB线*1

18B20温度传感器*1

杜邦线若干

接线图

|image25|

测试代码

::

   #include <OneWire.h>

   int DS18S20_Pin = 3;  // DS18B20温度传感器数据引脚连接数字口3
   OneWire ds(DS18S20_Pin);  // 创建OneWire实例

   void setup(void) 
   {
       Serial.begin(9600);  // 初始化串口通信，波特率9600
   }

   void loop(void) 
   {
       float temperature = getTemp();  // 获取温度值
       Serial.println(temperature);    // 输出温度值并换行
       delay(100);                    // 延时100毫秒
   }

   float getTemp()
   {
       byte data[12];  // 存储传感器数据
       byte addr[8];   // 存储传感器地址
       
       // 搜索传感器
       if (!ds.search(addr)) 
       {
           ds.reset_search();  // 重置搜索状态
           return -1000;       // 返回错误值
       }
       
       // 校验地址CRC
       if (OneWire::crc8(addr, 7) != addr[7]) 
       {
           Serial.println("CRC校验失败!");
           return -1000;
       }
       
       // 检查传感器类型
       if (addr[0] != 0x10 && addr[0] != 0x28) 
       {
           Serial.println("不支持的设备类型");
           return -1000;
       }
       
       // 开始温度转换
       ds.reset();
       ds.select(addr);
       ds.write(0x44, 1);  // 启动温度转换，寄生供电
       
       // 读取暂存器数据
       byte present = ds.reset();
       ds.select(addr);
       ds.write(0xBE);  // 读取暂存器
       
       // 读取9字节数据
       for (int i = 0; i < 9; i++) 
       {
           data[i] = ds.read();
       }
       
       ds.reset_search();
       
       // 计算温度值
       byte MSB = data[1];  // 高字节
       byte LSB = data[0];  // 低字节
       float tempRead = ((MSB << 8) | LSB);  // 合并两个字节
       float TemperatureSum = tempRead / 16; // 转换为实际温度值
       
       return TemperatureSum;
   }

测试结果

按照上图接好线，上传好代码，上电后，通电后，我们可在软件串口监视器中看到当前环境温度值，如下图。

.. |image1| image:: ./media/image-20250527113634546.png
.. |image-20250527115344256| image:: ./media/image-20250527115344256-1748503184856-7.png
.. |image-20250527115501137| image:: ./media/image-20250527115501137-1748503184856-8.png
.. |Snipaste_2025-05-30_11-37-22| image:: ./../../../驱动/media/Snipaste_2025-05-30_11-37-22.png
.. |image2| image:: media/eb385c638a1aa0b63971a8871b1bb907.png
.. |image3| image:: media/027da150683195e85b2f0dcdd879e0c1.png
.. |image4| image:: media/ef8fc4fed8c964bfd81cbdb2fce41285.jpeg
.. |image5| image:: media/befc72ced581329f53601ec57343858a.jpeg
.. |image6| image:: media/41be77ba1c82ed0db6aacfadd51680e4.jpeg
.. |image7| image:: media/81baffae5344681be2a5ab52f983a279.jpeg
.. |image8| image:: media/ab08793993dc185393f1fc33dca7dc91.jpeg
.. |image9| image:: media/2b5d3156ac58229a20b1c30a2c854a3c.jpeg
.. |image10| image:: media/e417a8a7130786b73f84e931b65b8e91.jpeg
.. |image11| image:: media/b9cedab4e47f7b6a89b2cb7fcb0a3785.jpeg
.. |image12| image:: media/ae94a6abfecf96fb43f51e263b44e524.jpeg
.. |image13| image:: media/2fcec7e45224cf0df6561905466d4f71.jpeg
.. |image14| image:: media/da17c1dfcaa509b4967232b12d24ccb4.jpeg
.. |image15| image:: media/139c18b5b1ad5808ed7d5b471b611dde.jpeg
.. |image16| image:: media/454f8df722c6e83ae9baaab6ce1a873f.jpeg
.. |image17| image:: media/eba008c0dc17fc0a8316a62c1bd28c7e.jpeg
.. |image18| image:: media/6db2d50d0551eeb8ecd02512393fe9b5.jpeg
.. |image19| image:: media/8d7ef1bdeb4b3eee0ef114b4b2918e12.jpeg
.. |image20| image:: media/9a5c65c1200a9211e8ea7f2b03d96a22.jpeg
.. |image21| image:: media/7b0f7373022f6c7e29ddda062f8b5815.jpeg
.. |image22| image:: media/fbbd0c4e254b376b37c67a81ae4a4fd8.jpeg
.. |image23| image:: media/82a92246a41526e768efa92757a1b269.jpeg
.. |image24| image:: media/c9e82713b33bc1da39dac480d2314764.jpeg
.. |image25| image:: media/9e70e746aa05ded51dab3a88780950d2.jpeg
