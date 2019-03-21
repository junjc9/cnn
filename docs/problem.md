# 存在的问题


> 基于模型（linear or bilinear）的方法
- 优点：重建结果完整，拓扑结构已知（这对于重建之后的应用很重要，如换脸，换表情等）
- 缺点：重建精度严重依赖所使用模型，而模型的训练对数据的采集及处理要求相当高。

> 基于多视图或者任何利用视觉信息估计深度的方法（stereo、mvs 、sfs...)

- 优点：处理的好的话精度可以很高（可能需多种技术辅助）
- 缺点：结果可能不完整，存在漏洞。拓扑结构不一致，后续应用较困难（具体看应用方向）。对人脸识别（对人脸识别并不很熟悉，以下纯属...）对有表情和大角度的人脸图像，可进行建模，然后生成中性表情的正脸照，提高识别精度。还有就是利用3dmm生成大角度下带有各种表情的图像做为训练数据。

## Other

- 1、光线问题

> 光照一直是机器视觉的老问题，对于人脸识别来说更是明显，由于人脸是一个3D的立体物，在不同方向和角度的光照下会增强或减弱脸部的某些特征，这就导致了机器读取的信息有偏差导致识别失败。


- 2、表情

> 姿态问题涉及头部在三维垂直坐标系中绕三个轴的旋转造成的面部变化，其中垂直于图像平面的两个方向的深度旋转会造成面部信息的部分缺失。而目前大多数算法主要是对于正面且准正的人脸来识别，如果当发生俯仰或者左右倾斜比较厉害时，算法的识别率会急剧下降。面部幅度较大的哭、笑、愤怒等表情变化同样影像着面部识别的准确率。

- 3、遮挡问题

> 由于人脸识别需要完整采集人脸的信息，而如果在有遮挡的情况下无法收集完整信息从而导致无法识别。拿IPhone X举例子，平时正常情况下拿起手机即可解锁，而在戴口罩时就会完全失效。其原因正是被采集出来的人脸图像有不完整，从而影响了后面的特征提取与识别，导致人脸检测算法的失效。

- 4、人脸相似性

> 全球人口众多，除了亲子关系长相相似，甚至有许多毫无血缘关系的人也有相似，这点对于利用人脸进行定位是有利的，但是对于利用人脸区分人类个体是不利的。

- 5、样本缺乏

> 基于统计学习的人脸识别算法是目前人脸识别领域中的主流算法，但是统计学习方法需要大量的训练。由于人脸图像在高维空间中的分布是一个不规则的流形分布，能得到的样本只是对人脸图像空间中的一个极小部分的采样，如何解决小样本下的统计学习问题有待进一步的研究。