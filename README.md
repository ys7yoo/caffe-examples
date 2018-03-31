
# caffe-examples

Put examples from [NVCaffe](https://github.com/NVIDIA/caffe) to here

Folder settings are sorted out.

Before running set `${CAFFE_ROOT}`.


## Setting on BIL servers

On BIL servers, add the following to your `~/.bashrc'.
```
export CAFFE_ROOT=/BIL/caffe
```

In addition, symbolic link for the built caffe tool is here.
```
sudo ln -s /BIL/caffe/build/tools/caffe /usr/local/bin/caffe
```

# Examples

## MNIST

1. Download data.
   ```
   data/mnist/get_mnist.sh
   ```
   
2. Generate lmdb files.
   ```
   examples/mnist/create_mnist.sh
   ```

3. Train 
   ```
   ${CAFFE_ROOT}/build/tools/caffe train --solver examples/mnist/lenet_solver.prototxt 
   ```
   
   On BIL servers, you can simply
   ```
   caffe train --solver examples/mnist/lenet_solver.prototxt 
   ```   
   
4. Test
   ```
   ${CAFFE_ROOT}/build/tools/caffe test -model examples/mnist/lenet_train_test.prototxt -weights examples/mnist/lenet_iter_10000.caffemodel -gpu 0 -iterations 100
   ```

   On BIL servers, you can simply
   ```
   caffe test -model examples/mnist/lenet_train_test.prototxt -weights examples/mnist/lenet_iter_10000.caffemodel -gpu 0 -iterations 100
   ```   

   ```
   I0401 01:07:55.807698 24408 caffe.cpp:335] Loss: 0.02727
   I0401 01:07:55.807709 24408 caffe.cpp:347] accuracy = 0.9917
   I0401 01:07:55.807723 24408 caffe.cpp:347] loss = 0.02727 (* 1 = 0.02727 loss)
   ```
   
   
See [Training LeNet on MNIST with Caffe](http://caffe.berkeleyvision.org/gathered/examples/mnist.html) for more information.


# Tutorial 
* [link](https://github.com/ys7yoo/BrainCaffe/wiki/Caffe-Tutorial-:-6.Interface-(Kor))
   
   




