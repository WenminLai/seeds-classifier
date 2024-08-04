Seed-classifier is a retrained resnet-18 model.It can classify among 4 different kinds of seeds:impatiens,sunflower,pea,peanut.This model is trained using Jetson-Nano.

Link to retrained resnet-18 model:
https://drive.google.com/file/d/1ozMH56gKX2sJjd-aq4vcq4qrXULtoSwn/view?usp=sharing

## Running this project
1.Clone the jetson-inference project from GitHub using "git clone --recursive https://github.com/dusty-nv/jetson-inference" and change directories into it
2.Make sure to have python packages installed using "sudo apt-get install libpython3-dev python3-numpy"
3.Make a build directory and run "cmake ../" in the build directory
4.Download the resnet18.onnx from the google drive link and download labels.txt from the models folder above to the Jetson Nano.
5.Create a directory named seeds in jetson-inference/python/training/classification/models
6.Move resnet18.onnx and labels.txt to the following directory: jetson-inference/python/training/classification/models/seeds
7.On your nano, navigate to the jetson-inference/python/training/classification directory.
8.Set NET=models/seeds
9.To classify an image, run "imagenet.py --model=$NET/resnet18.onnx --input_blob=input_0 --output_blob=output_0 --labels=$NET/labels.txt $IMAGE $OUTPUT", where $NET is the folder resnet18.onnx and labels.txt are stored, $IMAGE is the image file to classify, and $OUTPUT is the name of the file to output to.
