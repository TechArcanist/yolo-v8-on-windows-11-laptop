# yolo-v8-on-windows-11-laptop
Note: This project is currently a work in progress as I continue to learn and develop it. Until this note is removed, all data below or within this repository should be considered incomplete and not intended for use.

installation

1 # Install the ultralytics package from PyPI
pip install ultralytics

2 # Install the ultralytics package from GitHub
pip install git+https://github.com/ultralytics/ultralytics.git@main

3 check if it is installed yet or not

![image](https://github.com/user-attachments/assets/1f36fa93-9565-490f-abcd-7339ab1ad802)

C:\Windows\System32>python
Python 3.12.5 (tags/v3.12.5:ff3bc82, Aug  6 2024, 20:45:27) [MSC v.1940 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import ultralytics
>>> import torch
>>> torch.cuda.is_availaible()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: module 'torch.cuda' has no attribute 'is_availaible'. Did you mean: 'is_available'?
>>> torch.cuda.is_available()
True

4 predict a image like i iam training this image 
![iamgee](https://github.com/user-attachments/assets/c4bce161-686f-4392-b417-44a3d2218391)

i got this output

![iamgee](https://github.com/user-attachments/assets/0b47568b-d1c3-485d-8ce9-c67e243f6c7e)

image 1/1 D:\yoloooooo\iamgee.jpg: 384x640 10 persons, 1 baseball glove, 71.2ms
Speed: 3.0ms preprocess, 71.2ms inference, 174.4ms postprocess per image at shape (1, 3, 384, 640)
Results saved to D:\yoloooooo\output2


