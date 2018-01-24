# Caffe-ReLU6
Caffe Implementation of ReLU6 Layer, Required By MobileNetV2
## Utilize
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
## Experiments
I got top-1 error of 28.208% on imagenet using farmingyard's MobileNetV2 config(https://github.com/farmingyard/caffe-mobilenet_v2) with all ReLU Layers replaced by ReLU6 Layers, which is slightly better than the performance claimed in paper.
But my inference is really time-consuming caused by the ineffient caffe implementation of depthwise conv.

