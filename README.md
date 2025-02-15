# Baseline Methods for SuctionNet-1Billion

You can use your own camera on baseline methods in RA-L paper "SuctionNet-1Billion:  A  Large-Scale  Benchmark  for  Suction  Grasping" 


## Camera

Only realsense camera and kinect camera are required

## Environment

The code has been tested with `CUDA 11.2` and `pytorch 1.7.0` on ubuntu `16.04`

Others are on requirement.txt


*torch/torch vision install

```
pip install torch==1.7.1+cu110 torchvision==0.8.2+cu110 -f https://download.pytorch.org/whl/torch_stable.html
```

## Usage

### Neural Networks

Change the directory to `neural_network`:

```
cd neural_network
```
For inference, use the following command: 

```
python inference.py \ # inference_kinect.py or inference_realsense.py
--model model_name \
--checkpoint_path /path/to/the/saved/model/weights \
--camera realsense \ # realsense or kinect
--save_dir /path/to/save/the/inference/results \
--save_visu # whether to save the visualizations
```

or modify [scripts/deeplabv3plus_inference_kinect.sh](https://github.com/heechan99/suctionnet-baseline/blob/master/neural_network/deeplabv3plus_inference_kinect.sh), [scripts/deeplabv3plus_inference_realsense.sh](https://github.com/heechan99/suctionnet-baseline/blob/master/neural_network/inference_realsense.py), to inference with your kinect and realsense camera.


### Pre-trained Models

Graspnet/suctionnet-baseline provides models [realsense](https://drive.google.com/file/d/18TbctdhpNXEKLYDWFzI9cT1Wnhe-tn9h/view?usp=sharing), [kinect](https://drive.google.com/file/d/1gOz_KmIugBGUtpcyHAgYO01T0h5ZqOl9/view?usp=sharing), [Fully Conv Net for realsense](https://drive.google.com/file/d/1hgYYIvw5Xy-r5C8IitKizswtuMV_EqPP/view?usp=sharing). Just download it and put in weight file


## Citation


```
@ARTICLE{suctionnet,
  author={Cao, Hanwen and Fang, Hao-Shu and Liu, Wenhai and Lu, Cewu},
  journal={IEEE Robotics and Automation Letters}, 
  title={SuctionNet-1Billion: A Large-Scale Benchmark for Suction Grasping}, 
  year={2021},
  volume={6},
  number={4},
  pages={8718-8725},
  doi={10.1109/LRA.2021.3115406}}
```

