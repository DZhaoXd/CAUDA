# CAUDA
The implementation code of the paper ’Cluster Alignment with Target Knowledge Mining for Unsupervised Domain Adaptation Semantic Segmentation'

### Prerequisites
+ Create a conda virtual environment and activate it.
```
conda create --name uncertainty python=3.6
conda activate CAUDA
```
+ Install Pytorch and torchvision following the [official instructions](https://pytorch.org/), e.g.,
```
conda install pytorch==1.8.0 torchvision==0.6.0 cudatoolkit=10.1 -c pytorch
```
+ Install the dependent libraries.
```
pip install ninja yacs cython matplotlib tqdm opencv-python imageio mmcv
```

### Dataset Preparatation
Download the datasets GTA5 ([Download link](https://download.visinf.tu-darmstadt.de/data/from_games/)) and CityScapes ([Download link](https://www.cityscapes-dataset.com/)), then place them under the directory like:


```
semantic-segmentation/datasets
├── gta5
│   ├── images/
│   ├── labels/
│   └── gtav_label_info.p
└── cityscapes
    ├── gtFine/
    └── leftImg8bit/
...
```

### Getting Started


#### Train
The training code is coming soon.
    
#### Evaluation
+ Evaluate the performances on CityScapes.
```
# evaluate the last checkpoint (default)
python test_se.py -cfg configs/deeplabv2_ur101_src.yaml resume results/CAUDA/model_iter015000.pth

# evaluate all models
python test.py -cfg configs/deeplabv2_ur101_src.yaml resume results/CAUDA
```
The checkpoints and logs can be found at [link](https://drive.google.com/drive/folders/1Pn60zo9wAZ656KiuKeqtnkRZNQgbnqcM?usp=sharing).

### Acknowledge

The implementation is based on [FADA](https://github.com/JDAI-CV/FADA). Thanks for their great projects.
