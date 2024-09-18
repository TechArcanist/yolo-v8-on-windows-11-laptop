# YOLOv8 on Windows 11 Laptop

> **Note:** This project is currently a work in progress as I continue to learn and develop it. Until this note is removed, all data below or within this repository should be considered incomplete and not intended for use.

## 📦 Installation

1. **Install the ultralytics package at Terminal**

    ```bash
    pip install ultralytics
    ```

2. **Install the ultralytics package from GitHub**

    ```bash
    pip install git+https://github.com/ultralytics/ultralytics.git@main
    ```

3. **Check if it is installed correctly**

    ![Installation Check](https://github.com/user-attachments/assets/1f36fa93-9565-490f-abcd-7339ab1ad802)


4. **Predict an image**
   
      ```bash
      yolo task=detect mode=predict model=yolov8n.pt source='D:/yoloooooo/iamgee.jpg' save=True project='D:/yoloooooo' name='output' device=0
      ```
    - Example Image:
    
      ![Training Image](https://github.com/user-attachments/assets/c4bce161-686f-4392-b417-44a3d2218391)

    - Output:

      ![Prediction Output](https://github.com/user-attachments/assets/0b47568b-d1c3-485d-8ce9-c67e243f6c7e)

5 **Predict Using Live Camera**

```python
from ultralytics import YOLO

model = YOLO('yolov8n.pt')

results = model(source = 1, show=True , conf=0.4, save=True)
```

---

Feel free to contribute to this project or use it as a base for your own implementations!

<div align="center">
    <a href="https://github.com/TechArcanist/5-Tier-Secure-Lock-System">
        <img src="https://img.shields.io/badge/Clone_Repository-007ACC?style=for-the-badge&logo=github&logoColor=white" />
    </a>
</div>
