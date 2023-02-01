# 数据集介绍
## 商标图像数据的分布和构成
trademark_text共包含2000张商标图像，共计超过4000个标注实例。为了保持中英文的实例数量平衡，共有2260个英文实例和1943个中文实例。trademark_text主要是采集已公布的真实商标图样，同时商标图像中的文本为含有中文、英文、单字分布、水平文本、竖直文本、弯曲文本及艺术字等情形，同时文本和图形之间的空间分布可分为上下、上中下、左右以及镶嵌等情况，具体的数据集划分1750张作为训练集，250张作为测试集。
## 文件结构目录
trademark_text将所有数据划分为测试集test和训练集train，商标图像数据保存在text_image.zip压缩包中，标注文件保存在text_groundtruth.zip压缩包中。（由于训练集中包含1750张图像，超过github一次性传输大小限制，因此拆分成了两个文件，使用时下载并解压在text_image文件夹下即可）
```none
trademark_text
├── test
│   ├── text_groundtruth.zip
│   └── text_image.zip
└── train
    ├── text_image
    │   ├── text_image1.zip
    │   └── text_image2.zip
    └── text_groundtruth.zip
```
# 数据集标注
## 标注方式
如图所示，标注一个文本框共采用14个坐标点，分成两组，用7个坐标点来确定一条曲线。

首先确定文本行区域的四个顶点（1、2、3和4紫色点），然后使用五个坐标点（5、6、7、8和9绿色点）确定上边曲线，最后使用5个坐标点（10、11、12、13和14绿色点）确定下边曲线。

trademark_text对标注的区域增加了类别信息：0-英文、1-中文和2-图形

(x1,y1,x2,y2,x3,y3...x14,y14,c):前28个数每两个代表一个坐标点，c代表类别信息
<br/><div align=center><img src="https://github.com/kongbailongtian/trademark_text/blob/main/%E6%A0%87%E6%B3%A8%E7%A4%BA%E6%84%8F.jpg" width="600" align="center"/></div><br/>


## 样例
<br/><div align=left><img src="https://github.com/kongbailongtian/trademark_text/blob/main/example.jpg" width="300"/></div><br/>
```none
24,106,43,106,63,106,82,106,102,106,121,106,141,106,141,127,121,127,102,127,82,127,63,127,43,127,24,127,0
18,130,38,130,58,130,79,130,99,130,119,130,140,130,140,158,119,158,99,158,79,158,58,158,38,158,18,158,1
```
