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

Use **conda env list** find the path of cuda9.0
```shell
conda env list
```

```shell
(tf2) wxy@sait:~$ conda info -e
# conda environments:
#
cuda9.0                  /disk1/lx/conda/envs/cuda9.0
mk                       /disk1/lx/conda/envs/mk

```


Then change the **CONDA_ENV** to your path of cuda9.0
```shell
export CONDA_ENV="/disk1/lx/conda/envs/cuda9.0"
export CUDA_HOME="$CUDA_HOME:$CONDA_ENV/lib"
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:$CONDA_ENV/lib" 
```



Then source in you terminal.
```
source ~/.bashrc
```

## Third
### Download and unzip the file

  **Google-drive**: [tensorflow2.0-gpu-cudn9.0](https://drive.google.com/file/d/1QYHrotSqcvcTk1cvHp_eLajqFXkGIvw-/view?usp=sharing)


### Create a new env in conda(you can change **test** to your like)
```shell
conda create -n test python=3.7
conda activate test
pip install tensorflow-2.0.0-cp37-cp37m-linux_x86_64.whl
```

## Test
```python
python

import tensorflow as tf
tf.test.is_gpu_available()
```
If it shows True, congratulations.

### Error

```shell
W tensorflow/stream_executor/platform/default/dso_loader.cc:55] Could not load dynamic library 'libcusolver.so.9.0';.....undefined symbol: GOMP_critical_end;
```
If you have this error, please add follow code in your code.
```python
import tensorflow as tf
import ctypes
ctypes.CDLL("libgomp.so.1", mode=ctypes.RTLD_GLOBAL)
tf.test.is_gpu_available()

```

# How to install tensorflow2.0-GPU in your cuda version?
you need to bazel from the source code of tensorflow in your machine.

**Reference**

[my-blog](https://s-tm.cn/2019/09/28/%E9%82%A3%E4%BA%9B%E5%B9%B4%E8%B5%B0%E8%BF%87%E7%9A%84%E5%9D%91-tf2-gpu%E5%AE%89%E8%A3%85/)

[How to install tensorflow2.0 in cuda9?](https://github.com/tensorflow/tensorflow/issues/26418) 
