## 1.基础模型复现

### 经典算法

#### VOC2007
| Backbone         | Input Size  |          mAP                     | Model Size | Download  |
| :--------------: | :----------:|   :--------------------------:   | :--------: | :-------: |
|  yolo-vgg        |     320     |          63.4                    |       |   |
|  fast-rcnn(vgg)  |             |          73.2                    |       |   |
|  fast-rcnn(Res2Net-50)|     320     |     74.4%                   |       |   |
|  YOLO v2         |     320     |          78.6%                   |   29.9MB   |   |
|  YOLOv3(sync. BN + rand. shapes + cos. lr + lbl. smoothing + mixup) |     320     |          83.68%                   |      |   |



### 自己训练的模型的结果

| Backbone         | Input Size  |          mAP                     | Model Size | Download  |
| :--------------: | :----------:|   :--------------------------:   | :--------: | :-------: |
|  VGG16           |     300     |          77.75                    |   201MB    |   |
|  VGG16           |     512     |                                   |   207MB    |   |
|  Mobilenet V2    |     320     |                                   |   25.5MB   |   |
|  Mobilenet V3    |     320     |          69.46                    |   29.9MB   |   |
|  EfficientNet-B3 |     300     |          72.25                    |   97.1MB   |   |

### PASCAL VOC:

| Backbone         | Input Size  |          mAP                     | Model Size | Download  |
| :--------------: | :----------:|   :--------------------------:   | :--------: | :-------: |
|  VGG16           |     300     |          77.7                    |   201MB    | [model](https://github.com/lufficc/SSD/releases/download/1.2/vgg_ssd300_voc0712.pth)  |
|  VGG16           |     512     |          80.7                    |   207MB    | [model](https://github.com/lufficc/SSD/releases/download/1.2/vgg_ssd512_voc0712.pth)  |
|  Mobilenet V2    |     320     |          68.9                    |   25.5MB   | [model](https://github.com/lufficc/SSD/releases/download/1.2/mobilenet_v2_ssd320_voc0712_v2.pth) |
|  Mobilenet V3    |     320     |          69.5                    |   29.9MB   | [model](https://github.com/lufficc/SSD/releases/download/1.2/mobilenet_v3_ssd320_voc0712.pth) |
|  EfficientNet-B3 |     300     |          73.9                    |   97.1MB   | [model](https://github.com/lufficc/SSD/releases/download/1.2/efficient_net_b3_ssd300_voc0712.pth) |


### 结果对比
vgg16的原始网络基本持平，但是mobeilnet和efficientnet似乎表现出了比较难以收敛的特征；这种nas出来的网络的确计算量小，但是还是比较难优化；

## 2.加入特征融合层，如spp，csp，spanet，fpn，asff；以及使用darknet系列，peell系列网络；
- 实验目的，要验证如yolov5里面的csp，以及改进的spanet；结合其他新的backbone，以及特征融合算法看看在老模型的效果


## 3.多尺度训练；结合上面


## 4.调整loss，如回归用yolov2-v5的loss；验证focall-loss的效果


## 5.引入sam,maxout，mish，swish，leaky relu，gelu等新的激活函数

## 6.引入cutmix（76.7% voc2007）