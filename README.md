# Caffe-ReLU6
Caffe Implementation of ReLU6 Layer, Required By MobileNetV2
# Utilize
You should move .c* files to /path/to/caffe/src/caffe/layers/ and .hpp files to /path/to/caffe/include/caffe/layers/

Then add these lines to your caffe.proto file:

```
optional ReLU6Parameter relu6_param = 100000;
```
```
message ReLU6Parameter {
  optional float negative_slope = 1 [default = 0];
}
```
# Experiments on ImageNet
By using farmingyard's MobileNetV2(https://github.com/farmingyard/caffe-mobilenet_v2) configuration with  all ReLU layers replaced by ReLU6 layers, I got a Top-1 error of 28.208% on ImageNet-12 validation set.

