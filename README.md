# AICUP Baseline: BoT-SORT
### Prepare ReID Dataset

cd <BoT-SORT_dir>
python fast_reid/datasets/generate_AICUP_patches.py --data_path <dataets_dir>/AI_CUP_MCMOT_dataset/train


### Train the ReID Module for AICUP

```shell
cd <BoT-SORT_dir>
# For training AICUP 
python fast_reid/tools/train_net.py --config-file fast_reid/configs/AICUP/bagtricks_R50-ibn.yml MO
# AICUP Baseline: BoT-SORT epoch = 60


cd <BoT-SORT_dir>
python fast_reid/datasets/generate_AICUP_patches.py --data_path <dataets_dir>/AI_CUP_MCMOT_dataset/train


### Train the ReID Module for AICUP

```shell
cd <BoT-SORT_dir>
# For training AICUP 
python fast_reid/tools/train_net.py --config-file fast_reid/configs/AICUP/bagtricks_R50-ibn.yml MO
# AICUP Baseline: BoT-SORT epoch = 60

```

### Fine-tune YOLOv7 for AICUP

[`yolov7_training.pt`](https://github.com/WongKinYiu/yolov7/releases/download/v0.1/yolov7-w6_training.pt) [`yolov7-e6_training.pt`]


``` shell
# finetune p6 models
python train_aux.py --device 0 --batch-size 8 --data .\data\mydata.yaml --img 1280 720 --cfg .\cfg\training\yolov7-e6.yaml --hyp .\data\hyp.scratch.p5.yaml --weights .\weight\yolov7-e6.pt
```

The training results will be saved by default at `runs/train`.

## Tracking and creating the submission file for AICUP (Demo)

```shell
cd <BoT-SORT_dir>
bash tools/track_all_timestamps.sh --weights "pretrained/yolov7-e6e.pt" --source-dir "AI_CUP_MCMOT_dataset/train/images" --fast-reid-config "fast_reid/configs/AICUP/bagtricks_R50-ibn.yml" --fast-reid-weights "logs/AICUP/bagtricks_R50-ibn/model_0058.pth"
```













