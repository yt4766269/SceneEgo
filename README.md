# SceneEgo

Official implementation of paper: 

**Scene-aware Egocentric 3D Human Pose Estimation**

*Jian Wang, Diogo Luvizon, Weipeng Xu, Lingjie Liu, Kripasindhu Sarkar, Christian Theobalt*

*CVPR 2023*

![Demo image](./resources/Wang_CVPR_2023.gif)

### Install

1. Create a new anaconda environment

```shell
conda create -n sceneego python=3.9

conda activate sceneego
```

2. Install pytorch 1.13.1 from https://pytorch.org/get-started/previous-versions/

3. Install other dependencies
```shell
pip install -r requirements.txt
```
### Run the demo

1. Download pre-trained pose estimation model from  under ```models/sceneego/checkpoints```

2. run:
```shell
python demo.py --config experiments/sceneego/test/sceneego.yaml --img_dir data/demo/imgs --depth_dir data/demo/depths --output_dir data/demo/out --vis True
```
The result will be shown with the open3d visualizer and the predicted pose is saved at ```data/demo/out```.

3. The predicted pose is saved as the pkl file. To visualize the predicted result (e.g. predicted pose saved as ```1.pkl```), run:
```shell
python visualize.py --img data/input/img/1.jpg --depth data/input/depth/1.jpg --out data/output/1.pkl
```
The result will be shown with the open3d visualizer.

### Test on real-world dataset

1. Download pre-trained pose estimation model from  under ```models/sceneego/checkpoints```

2. Download the test dataset from to ```data/sceneego```

3. run:
```shell
python test.py --data_path data/sceneego
```






