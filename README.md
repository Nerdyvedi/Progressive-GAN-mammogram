# Progressive-GAN-mammogram
Implementing Progressive GAN to generate mammogram images

## How to Use
__[step 1.] Prepare dataset__
~~~
------------------------------------------
The training data folder should look like : 
<train_data_root>
                |--Your Folder
                        |--image 1
                        |--image 2
                        |--image 3 ...
------------------------------------------
~~~
__[step 2.] Prepare environment using virtualenv__   
  + you can easily set PyTorch (v0.3) and TensorFlow environment using virtualenv.
  + CAUTION: if you have trouble installing PyTorch, install it mansually using pip. [[PyTorch Install]](http://pytorch.org/)
  + For install please take your time and install all dependencies of PyTorch and also install tensorflow
  
  ~~~
  $ virtualenv --python=python2.7 venv
  $ . venv/bin/activate
  $ pip install -r requirements.txt
  $ conda install pytorch torchvision -c pytorch
  ~~~

__[step 3.] Run training__      
+ edit `config.py` to change parameters. (don't forget to change path to training images)
+ specify which gpu devices to be used, and change "n_gpu" option in `config.py` to support Multi-GPU training.
+ run and enjoy!  

~~~~
  (example)
  If using Single-GPU (device_id = 0):
  $ vim config.py   -->   change "n_gpu=1"
  $ CUDA_VISIBLE_DEVICES=0 python trainer.py
  
  If using Multi-GPUs (device id = 1,3,7):
  $ vim config.py   -->   change "n_gpu=3"
  $ CUDA_VISIBLE_DEVICES=1,3,7 python trainer.py
~~~~

__[step 4.] Generate fake images using linear interpolation__   
~~~
CUDA_VISIBLE_DEVICES=0 python generate_interpolated.py
~~~
  
 
