# Caffe-ReLU6
Caffe Implemantation of ReLU6 Layer, Required By MobileNetV2
# Utilize
You should move .c* files to src/caffe/layers and .hpp files to include/caffe/layers,Then add these lines to you caffe.proto file:
{ {{optional ReLU6Parameter relu6_param = 100000;
message ReLU6Parameter {
  optional float negative_slope = 1 [default = 0];
}}} }



