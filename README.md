# Caffe-MobileNetV2-ReLU6
Caffe Implementation of ReLU6 Layer, Required By MobileNetV2.
## ReLU6 Utilize
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
## Experiments On ImageNet
I got top-1 error of 28.208% on imagenet which is slightly better than the performance claimed in paper(https://arxiv.org/abs/1801.04381).

I trained my model using farmingyard's MobileNetV2 config(https://github.com/farmingyard/caffe-mobilenet_v2) but replacing all ReLU Layers by ReLU6 Layers.

But my inference is really time-consuming mainly caused by the ineffient caffe implementation of depthwise conv.

