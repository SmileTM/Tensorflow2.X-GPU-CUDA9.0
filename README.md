# Tensorflow2.0-GPU-CUDA9.0
Tensorflow2.0-GPU-CUDA9.0

This Tensorflow2.0-GPU-CUDA9.0 is bazel from the sorce code of Google. 



# Install

## First  
### Create cuda9.0 environment by conda
```shell
conda create -n cuda9.0
conda activate cuda9.0
conda install cudatoolkit=9.0 cudnn cupti
```

## Second
### Add dependency in .bashrc

use **conda env list** find the path of cuda9.0
```shell
conda env list
```

Then change the **CONDA_ENV** to your path of cuda9.0
```shell
export CONDA_ENV=path/envs/cuda9.0
export CUDA_HOME=$CUDA_HOME:$CONDA_ENV/lib
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_ENV/lib 
```
Then source in you terminal.
```
source ~/.bashrc
```

## Third
### download and unzip the file

  **Google-drive**: [tensorflow2.0-gpu-cudn9.0](https://drive.google.com/file/d/1QYHrotSqcvcTk1cvHp_eLajqFXkGIvw-/view?usp=sharing)


### create a new env in conda(you can change env to your like)
```shell
conda create -n env python=3.7
conda activate env
pip install tensorflow-2.0.0-cp37-cp37m-linux_x86_64.whl
```

## Test
```python
import tensorflow as tf
tf.test.is_gpu_available()
```


# How to install tensorflow2.0-GPU in your cuda version?
you need to bazel from the source code of tensorflow in your machine.

**reference**

[my-blog](https://s-tm.cn/2019/09/28/%E9%82%A3%E4%BA%9B%E5%B9%B4%E8%B5%B0%E8%BF%87%E7%9A%84%E5%9D%91-tf2-gpu%E5%AE%89%E8%A3%85/)

[How to install tensorflow2.0 in cuda9?](https://github.com/tensorflow/tensorflow/issues/26418) 
