# yolo-v8-on-windows-11-laptop

installation

# Install the ultralytics package from PyPI
pip install ultralytics

# Install the ultralytics package from GitHub
pip install git+https://github.com/ultralytics/ultralytics.git@main

check if it is ninstalled yet or not

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

