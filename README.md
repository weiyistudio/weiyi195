# weiyi195
基于机器学习的人脸性别识别的设计与实现

# 基于机器学习的人脸性别识别的设计与实现

#### 介绍
   

本毕业设计主要研究基于机器学习算法的人脸性别识别。人脸性别识别是人脸识别的重要组成部分，也是模式识别与计算机视觉领域的研究热点，它在监控设备，智能人工对话和自动人口数据收集等领域有着广泛的应用。作为人的重要生物特征，人脸蕴含着大量的信息，例如性别、年龄、身份等等。
本项目将分为以下几个步骤。1.开源人脸数据库资源收集 2. 图像处理 3.图像标记 4.图像特征提取5.使用多种机器学习算法（神经网络，支持向量机，最近邻居法，逻辑回归）来搭建分类器6.对算法优劣与准确率进行对比与总结。本毕业设计主要使用软件MATLAB 与 python 完成。 其中图像特征提取使用MATLAB， 搭建分类器使用python。
这个项目的主要目的是建立一个分类器。它可以处理人的面部图片并告诉我们图片中人的性别。该项目中，我们有两个主要步骤，即特征提取和分类算法的实现。特征提取处理图像并分析像素以尝试检测模式。分类器使用这些模式并确定人脸的性别。结果表明，计算机可以学习图像的模式，分类器可以在实践中使用。未来的方向是为了提高分类器检测性别的准确率。






#### 项目说明


特征提取处理图像并分析像素以尝试检测图案。我们可以使用表示图像特征的提取图案对图像进行分类。我们使用特征提取的原因是它从图像中提取特征。以人脸图像为例，我们可以查找人脸的边缘，人脸上的纹理和人脸的不同颜色。特征提取将帮助我们检测图片的这些特征。这些提取的特征能够理解疾病的征兆。通过分析图片，特征提取使计算机识别出男女图片的区别，即我们如何检测人脸性别。详细代码见附录。

LBP，全称是局部二值模式，是一种提取图像局部特征的方法。它有很多应用，如人脸识别，面部表情识别。我们需要提取局部特征的原因是，一幅图像的信息量大，计算机难以处理复杂的信息。因此，我们需要提取LBP功能。
LBP是一种局部特征，它表示像素与其相邻像素之间的关系。以基本LBP为例，说明像素灰度值与灰度值的八个相邻像素值之间的关系。原始的LBP算子定义在像素3*3的邻域内，以邻域中心像素为阈值，相邻的8个像素的灰度值与邻域中心的像素值进行比较，若周围像素大于中心像素值，则该像素点的位置被标记为1，否则为0。

灰度共生矩阵(GLDM)的统计方法是20世纪70年代初由R.Haralick等人提出的，它是在假定图像中各像素间的空间分布关系包含了图像纹理信息的前提下，提出的具有广泛性的纹理分析方法。
度共生矩阵被定义为从灰度为i的像素点出发，离开某个固定位置（相隔距离为d，方位为）的点上灰度值为的概率，即，所有估计的值可以表示成一个矩阵的形式，以此被称为灰度共生矩阵。对于纹理变化缓慢的图像，其灰度共生矩阵对角线上的数值较大；而对于纹理变化较快的图像，其灰度共生矩阵对角线上的数值较小，对角线两侧的值较大。由于灰度共生矩阵的数据量较大，一般不直接作为区分纹理的特征，而是基于它构建的一些统计量作为纹理分类特征。Haralick曾提出了14种基于灰度共生矩阵计算出来的统计量：即：能量、熵、对比度、均匀性、相关性、方差、和平均、和方差、和熵、差方差、差平均、差熵、相关信息测度以及最大相关系数。
由于纹理是由灰度分布在空间位置上反复出现而形成的，因而在图像空间中相隔某距离的两像素之间会存在一定的灰度关系，即图像中灰度的空间相关特性。灰度共生矩阵就是一种通过研究灰度的空间相关特性来描述纹理的常用方法。灰度共生矩阵是涉及像素距离和角度的矩阵函数，它通过计算图像中一定距离和一定方向的两点灰度之间的相关性，来反映图像在方向、间隔、变化幅度及快慢上的综合信息。

![输入图片说明](https://images.gitee.com/uploads/images/2021/1028/001133_16076fab_8650135.png "屏幕截图.png")

神经网络的基本单元是感知器，将感知器组合在一起就构成了庞大的神经网络。在现代意义上，感知器是用于学习二元分类器的算法：将其输入x（实值向量）映射到输出值f（x）的函数（单个二进制值）

本项目整合四种机器学习算法，并对其进行改进。算法描述如下：
当一张图片输入到计算机，我们同时用四种机器学习算法进行识别。对于男性图片，如果有至少三种算法识别出它为男性，那么我们才说这是一次正确的识别。其余情况都为错误的识别。对于女性图片，如果有至少三种算法识别出它为女性，那么我们才说这是一次正确的识别，其余情况都为错误的识别。


#### 项目截图

Matlab是一个高级的矩阵/阵列语言，它包含控制语句、函数、数据结构、输入和输出和面向对象编程特点。用户可以在命令窗口中将输入语句与执行命令同步，也可以先编写好一个较大的复杂的应用程序（M文件）后再一起运行。新版本的MATLAB语言是基于最为流行的C++语言基础上的，因此语法特征与C++语言极为相似，而且更加简单，更加符合科技人员对数学表达式的书写格式。使之更利于非计算机专业的科技人员使用。而且这种语言可移植性好、可拓展性极强，这也是MATLAB能够深入到科学研究及工程计算各个领域的重要原因。

![输入图片说明](https://images.gitee.com/uploads/images/2021/1028/001225_364772ea_8650135.png "屏幕截图.png")

![输入图片说明](https://images.gitee.com/uploads/images/2021/1028/001232_555a339e_8650135.png "屏幕截图.png")

#### 求助热线




代码有任何问题可联系
联系Q：2762501186

                            
![输入图片说明](https://images.gitee.com/uploads/images/2020/1119/003728_cd598bb9_4865385.jpeg "微信.jpg")       

![输入图片说明](https://images.gitee.com/uploads/images/2021/1026/221249_847cb212_8650135.png "屏幕截图.png")


    

感谢Gitee！！  
觉得项目不错的给个Star谢谢大佬！！！
提供无偿review服务
限时加好友入群！！！
