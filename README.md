# aicup
# AI Cup - YOLOv7 Training

## Running Training Code

```bash
python train_aux.py --device 0 --batch-size 8 --data .\data\mydata.yaml --img 1280 720 --cfg .\cfg\training\yolov7-e6.yaml --hyp .\data\hyp.scratch.p5.yaml --weights .\weight\yolov7-e6.pt


运行代码前需要下载预训练权重
https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-e6.pt
将权重放到文件夹中，修改训练代码的--weights为权重位置
修改data\mydata.yaml,将Dataset位置修改为你的Dataset位置

Instructions
Download Pre-trained Weights:
Download the pre-trained weights from the following link:
[YOLOv7-e6 Pre-trained Weights](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-e6.pt)

Place Weights in Folder:
Place the downloaded weights file in the desired folder.

Modify Training Code:
Update the --weights parameter in the training command to point to the location of the weights file.
