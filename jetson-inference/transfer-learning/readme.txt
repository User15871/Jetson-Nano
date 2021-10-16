$ sudo apt-get update
$ sudo apt-get install git cmake libpython3-dev python3-numpy
$ git clone --recursive https://github.com/dusty-nv/jetson-inference
$ cd jetson-inference
$ mkdir build
$ cd build
$ cmake ../
$ make -j4
$ sudo make install
$ sudo ldconfig
$cd jetson-inference/python/training/classification
$ython3 train.py --model-dir models/no_nomask ~/Desktop/dataset/
$python3 onnx_export.py --model-dir=models/no_nomask/
$vi labels.txt
$imagenet --model=models/no_nomask/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=labels.txt ~/Desktop/without_mask.jpeg ~/Desktop/output_3.jpg
