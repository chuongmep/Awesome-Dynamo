---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Tensorflow

TensorFlow is a free and open-source software library for machine learning and artificial intelligence. It can be used across a range of tasks but has a particular focus on training and inference of deep neural networks. [wikipedia](https://en.wikipedia.org/wiki/TensorFlow)

## Install Tensorflow

You need ensure that card in computer support Tensorflow before want install it: [https://developer.nvidia.com/cuda-gpus](https://developer.nvidia.com/cuda-gpus)

I recommend you should use card **RTX** at the momment. First at all, you need install tensorflow : 

```bash
pip install tensorflow
```

## Install Cuda

You need install cuda and cudnn before work with tensorflow, because tensor need GPU to use for process.

- Cuda : [https://developer.nvidia.com/cuda-toolkit](https://developer.nvidia.com/cuda-toolkit)

- CUDNN : [https://developer.nvidia.com/cudnn](https://developer.nvidia.com/cudnn)

**Warning** : 

- Please download version map with version of tensorflow, see at [https://www.tensorflow.org/install/source#gpu](https://www.tensorflow.org/install/source#gpu)/
- Please download tensorflow map with version python, see at : [https://www.tensorflow.org/install/source_windows#tested_build_configurations](https://www.tensorflow.org/install/source_windows#tested_build_configurations)

To check Cuda version installed in computer, let use command:

``` bash
nvidia-smi
nvcc --version
```
When Cuda intalled sucessfully , now you can check tensorflow is supported tensorfllow version and gpu support. In code sample bellow , I will check version of python,pandas,tensorflow and list gpu supported.

```{code-cell} ipython3
import sys

import tensorflow.keras
import pandas as pd
import sklearn as sk
import tensorflow as tf

print(f"Tensor Flow Version: {tf.__version__}")
print(f"Keras Version: {tensorflow.keras.__version__}")
print()
print(f"Python {sys.version}")
print(f"Pandas {pd.__version__}")
print(f"Scikit-Learn {sk.__version__}")
gpu = len(tf.config.list_physical_devices('GPU'))>0
print("GPU is", "available" if gpu else "NOT AVAILABLE")
```
## Start with Tensorflow

```{code-cell} ipython3
import tensorflow as tf
print(tf.__version__)
msg = tf.constant("Hello TesorFlow")
tf.print(msg)
x1 = tf.constant([1,2,3,4])
x2 = tf.constant([5,6,7,8])
result = tf.multiply(x1,x2)
print(result)
#OUT = result 
```

Use GPU inside tensorflow :

```{code-cell} ipython3
tf.debugging.set_log_device_placement(True)

gpus = tf.config.list_logical_devices('GPU')
if gpus:
  # Replicate your computation on multiple GPUs
  c = []
  for gpu in gpus:
    with tf.device(gpu.name):
      a = tf.constant([[1.0, 2.0, 3.0], [4.0, 5.0, 6.0]])
      b = tf.constant([[1.0, 2.0], [3.0, 4.0], [5.0, 6.0]])
      c.append(tf.matmul(a, b))
  with tf.device('/CPU:0'):
    matmul_sum = tf.add_n(c)
    print(matmul_sum)
```
- Read more discusstion at :

[https://forum.dynamobim.com/t/is-python-3-in-dynamo-use-gpu-or-cpu/69619/11](https://forum.dynamobim.com/t/is-python-3-in-dynamo-use-gpu-or-cpu/69619/11)

[https://medium.com/@medasuryatej/install-tensorflow-gpu-2-0-f4e215438199](https://medium.com/@medasuryatej/install-tensorflow-gpu-2-0-f4e215438199)
