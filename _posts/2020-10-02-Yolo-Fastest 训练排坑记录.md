---
layout: post
title:  "Yolo-Fastest 训练排坑记录"
categories: Object-Detection
tags: yolo-fastest
author: Zhenyu ZHAO
---

* content
{:toc}




### Yolo-Fastest链接

 <a href="https://github.com/dog-qiuqiu/Yolo-Fastest"  target="opentype">https://github.com/dog-qiuqiu/Yolo-Fastest</a>

### 环境配置

标准的darknet框架开发环境，只要系统有C语言的编译环境就可以直接完成基于CPU进行计算的框架编译。在Linux系统下进行开发相对来说更方便一些(下文中的系统环境为Ubuntu 18.04)。

如果要用视频或摄像头进行测试，需要先**编译安装**好OPENCV，之后在Makefile中使OPENCV=1。虽然不使用OPENCV也可以进行训练，但后期测试中总会用到OPENCV，所以建议装好OPENCV后编译。

如果需要GPU加速计算，则需要先**安装Cuda和CuDNN**，并在Makefile中使GPU=1，并使CUDNN=1。同时将Makefile中的 

```
NVCC=nvcc
```

改向系统中cuda路径下的nvcc，比如：

```
NVCC=/usr/local/cuda-9.0/bin/nvcc
```

如果有好一些的GPU，建议一定要使用GPU，亲测1080Ti比单纯运行在i7-1065G7上快上十几倍。

轻推一个计算平台-易学智能 <a href="https://www.easyaiforum.cn/ "  target="opentype">https://www.easyaiforum.cn/</a>在1080Ti的配置下有darknet开发环境，不用安装opencv和cuda、cudnn，并且有窗口化操作界面。缺点是贵、上传下载速度慢、存储设计有些不合理。还算比较适合一些短时间的训练测试任务。

### 数据集准备

（个人用的方法比较笨重，其实可以直接生成包含目标位置标注信息的txt文件，但没有测试过，所以只记录了笨重但可用的方法。 直接生成的方法可以考虑使用 LabelImg直接进行Yolo格式的标注。推一个朋友开源的视频标注程序 <a href="https://github.com/xinyang-go/VideoMarking"  target="opentype">https://github.com/xinyang-go/VideoMarking</a> ）

假设已经准备好了一个文件夹的图片文件。（如果没有准备好，可以用录像设备录些视频，然后按帧提取出来）

那么可以开始以下步骤：

1. 创建一个用于存放xml文件（将会存储图片中目标物的像素位置信息）的文件夹。

2. 安装 LabelImg :  <a href="https://github.com/tzutalin/labelImg"  target="opentype">https://github.com/tzutalin/labelImg</a>。

3. 在LabelImg界面下点击Open Dir打开存放图片的文件夹。点击Change Save Dir打开用于存放xml文件的文件夹。

4. 使用LabelImg以PascalVOC格式进行标注。

   <center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/labelImg.PNG"  height="270" width="450" >    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">图1 LabelImg标注</div> </center>

5. 将完成标注后的文件夹放到Yolo-Fastest目录下。由于LabelImg生成的xml文件中的图片路径为绝对路径，所以放到新的位置后xml文件中的路径需要修改。可以参考<a href="https://www.jianshu.com/p/cf12bef0872c"  target="opentype">https://www.jianshu.com/p/cf12bef0872c</a>，将所有xml文件中的图片路径改成当前的图片路径（记得随便打开一个xml文件检查一下）。

6. **(这一步是需要改/写一些程序的)**生成训练用的图片目录文件train.txt（用于训练）、trainval.txt（用于训练过程中的验证）和Yolo读取的包含目标标注信息的txt文件。可以参考<a href="https://blog.csdn.net/hesongzefairy/article/details/107183162"  target="opentype">https://blog.csdn.net/hesongzefairy/article/details/107183162</a>，但是**需要注意的是**这个链接里的"maketxt.py"会生成四个txt文件，train.txt、trainval.txt、test.txt、val.txt，训练集一定要选用train.txt，如果数据集小验证集建议直接用trainval.txt（比例可以通过trainval_percent来调节，这两组是不相互重复的，如果需要测试，建议再做一些图片来做）。

   **！而且 "maketxt.py"文件生成txt文件会只存储不包含路径和拓展名的图片名称，但训练中需要存储的是完整的路径(从Yolo-Fastest根目录开始的相对路径或绝对路径)、名称。**

   链接中的"voc_label.py"是用来在存储图片的文件夹中生成包含目标标注信息的txt文件的，它需要使用"maketxt.py"生成的txt文件，**注意**不仅要生成train.txt中包含的图片的标注信息**还要生成**验证集的trainval.txt中包含的标注信息。

   **完成"voc_label.py"的标注信息文件生成后，修改并使用修改后的maketxt.py来生成包含完整路径、名称的train.txt、trainval.txt**

完成以上步骤后应该会有的训练所需的必要东西为： 一个存有图片和包含目标标注信息txt文件的文件夹（见图2）（每张图片应该都有一个对应的txt!）、其中txt文件的内容示例如图3、一个train.txt文件（内容示例见图4）、一个trainval.txt文件（内容示例见图5）。

<center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/Imagesdirectory.png"  height="270" width="450" >    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">图2 图片及标注信息文件夹</div> </center>

 <center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/txtmessage.png"  height="270" width="450" >    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">图3 000000.txt中内容(一种目标)</div> </center>

 <center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/traintxt.png"  height="270" width="450" >    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">图4 train.txt中内容</div> </center>

 <center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/trainvaltxt.png"  height="270" width="450" >    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">图5 trainval.txt中内容</div> </center>

### 训练

下面是比较具体的步骤：

   1. 建议将yolo-fastest.cfg、yolo-fastest.weights从 *Yolo-Fastest根目录/Yolo-Fastest/VOC/* 下各复制一份到  *Yolo-Fastest根目录*  下进行后续的修改。并将voc.data、voc.names从 *Yolo-Fastest根目录/data* 下各复制一份到 *Yolo-Fastest根目录*  下进行修改。这样后面可以直接在 *Yolo-Fastest根目录*  下执行作者给出的训练指令，否则这些指令中的文件应该加上路径。

   2. 修改yolo-fastest.cfg。假设不修改网络结构，需要改的有以下部分：

      第834行：

      ```
      修改前： filters = 75   修改后：filters = 6*(5+类别数)*0.5  比如如果只有一类就改成： filters = 18 
      ```

      第841行：

      ```
      修改前：classes = 20 修改后：classes = 类别数 比如只有一类就改成：classes = 1
      ```

      第910行：

      ```
      修改前： filters = 75   修改后：filters = 6*(5+类别数)*0.5  比如如果只有一类就改成： filters = 18 
      ```

      第917行：

      ```
      修改前：classes = 20 修改后：classes = 类别数 比如只有一类就改成：classes = 1
      ```

      修改后记得保存。

   3. 修改voc.data。

      修改前：

      ```
      classes = 20
      train = /home/pjreddie/data/voc/train.txt
      valid = /hone/pjreddie/data/voc/2007.txt
      names = data/voc.names
      backup = /home/pjreddie/backup/
      ```

      修改后：

      ```
      classes = 类别数
      train = 上面数据集准备中得到的train.txt的路径
      valid = 上面数据集准备中得到的trainval.txt的路径
      names = voc.names的路径
      backup = ./backup/
      ```

      比如，假如只有一类目标，并且voc.names将放在 *Yolo-Fastest根目录*  下，按照图3、图4中的路径信息应该改成：

      ```
      classes = 1
      train = ./train/Main/train.txt
      valid = ./train/Main/trainval.txt
      names = ./voc.names
      backup = ./backup/
      ```

   4. 修改voc.names

      这个只要把voc.names中按顺序改成标注的所有标签即可。

      修改前：

      ```
      aeroplane
      bicycle
      bird
      boat
      bottle
      bus
      car
      cat
      chair
      cow
      diningtable
      dog 
      horse
      motorbike
      person
      pottedplant
      sheep
      sofa
      train
      tvmonitor
      ```

      **假如**只有一类目标，名称为Gun(如图1)，修改后的应为：

      ```
      Gun
      ```

   5. 生成预训练模型

      在**编译好的** *Yolo-Fastest根目录*  下执行：

      ```
      ./darknet partial yolo-fastest.cfg yolo-fastest.weights yolo-fastest.conv.109 109
      ```

      

   6. 开始训练

      执行：

      ```
        ./darknet detector train voc.data yolo-fastest.cfg yolo-fastest.conv.109 
      ```

训练中每1000代会在backup文件夹中生成一个权重文件，训练中的最新权重文件也会存储。 

在不改变作者设定的所有其他参数的条件下，个人用681张训练图片，75张验证图片标注一类目标做了简易测试，大概 7000 epochs 左右达到了相对好的收敛效果，在1080Ti上约消耗5小时。avg loss下降到了0.02左右。

### 简易测试

修改作者video_yolov3.sh脚本中的各种配置文件、权重文件为训练后得到的权重文件后在树莓派4B上的推理效果：图6。因为数据集制作很差，所以没有做精确测试，可以参照作者的测试表格。

 <center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/Gun_without_NCNN.gif"  height="254" width="362" >    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">图6 树莓派4B推理效果</div> </center>

### NCNN加速

 NCNN是腾讯开源的一款推理优化框架，Yolo-Fastest作者给出了一个效果示例 <a href="https://github.com/dog-qiuqiu/Yolo-Fastest/tree/master/ncnn_sample"  target="opentype">https://github.com/dog-qiuqiu/Yolo-Fastest/tree/master/ncnn_sample</a>

**注意** README.md中的指示因为markdown 语言的特性显示的不完整，完整的指令应该是：

```
g++ -o yolo-fastest yolo-fastest.cpp -I include/ncnn/ lib/libncnn.a `pkg-config --libs --cflags opencv` -fopenmp
```

 **注意** 如果使用的是OPENCV4.*，则应为：

```
g++ -o yolo-fastest yolo-fastest.cpp -I include/ncnn/ lib/libncnn.a `pkg-config --libs --cflags opencv4` -fopenmp
```

执行上述语句之前，应该先编译安装ncnn <a href="https://github.com/Tencent/ncnn"  target="opentype">https://github.com/Tencent/ncnn</a>

 **注意** 如果是在树莓派的64位Ubuntu Mate系统上编译 应该依照 "Build for ARM Cortex-A family with cross-compiling"->"AArch64 GNU/Linux target (aarch64-linux-gnu)"。

**编译后将build目录下的install文件夹中的include和lib复制到Yolo-Fastest中的ncnn_sample文件夹下**才能在ncnn_sample中正常执行上述指令。

将自己训练后的网络转换参考<a href="https://github.com/Tencent/ncnn/tree/master/tools/darknet"  target="opentype">https://github.com/Tencent/ncnn/tree/master/tools/darknet</a>

运行转换后的网络，可以参考作者给的示例。把yolo-fastest.cpp中的类别、网络路径改掉，编译就能正常运行，这里不作赘述了。

加速后的网络在树莓派4B上的推理效果如图7。



 <center>    <img style="border-radius: 0.3125em;    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"     src="https://github.com/Hideousmon/Hideousmon.github.io/raw/master/_img/posts/Gun_with_NCNN.gif"  height="254" width="362" >    <br>    <div style="color:orange; border-bottom: 1px solid #d9d9d9;    display: inline-block;    color: #999;    padding: 2px;">图7 NCNN加速下的树莓派4B推理效果</div> </center>





