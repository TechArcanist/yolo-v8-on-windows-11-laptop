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

5. **Predict Using Live Camera**

```python
from ultralytics import YOLO

model = YOLO('yolov8n.pt')

results = model(source = 1, show=True , conf=0.4, save=True)
```
![image](https://github.com/user-attachments/assets/172ae877-f2a7-4576-bc14-21c1dba66cc0)

---

6. **Video Implementation**
```python
from ultralytics import YOLO
import cv2

model = YOLO("yolov8n-seg.pt")

video_path = "moving_cars.mp4" 
cap = cv2.VideoCapture(video_path)

if not cap.isOpened():
    print(f"Error: Could not open video {video_path}")
    exit()

frame_width = int(cap.get(cv2.CAP_PROP_FRAME_WIDTH))
frame_height = int(cap.get(cv2.CAP_PROP_FRAME_HEIGHT))
fps = int(cap.get(cv2.CAP_PROP_FPS))

output_path = "segmented_output.mp4"  
fourcc = cv2.VideoWriter_fourcc(*'mp4v') 
out = cv2.VideoWriter(output_path, fourcc, fps, (frame_width, frame_height))

while cap.isOpened():
    success, frame = cap.read() 
    if success:
        
        results = model(frame)

        
        annotated_frame = results[0].plot() 


        out.write(annotated_frame)

        
        cv2.imshow("YOLOv8 Segmentation", annotated_frame)

        
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break
    else:
        break  


cap.release()
out.release()
cv2.destroyAllWindows()

print(f"Video saved to {output_path}")

https://github.com/user-attachments/assets/d35a5f69-f8da-4a34-bc2c-918e8ceff03c
```
7. Segmentation of a Video
    Like we saw in above example it has just drawn a box around the cars but in segmentation model it tells according to the pixels . It uses **segmentation models** when you need pixel-perfect information     about objects or their boundaries.
```python
from ultralytics import YOLO

import cv2

  
  

model = YOLO("yolov8n-seg.pt")

  

video_path = "moving_cars.mp4"

cap = cv2.VideoCapture(video_path)

  

if not cap.isOpened():

    print(f"Error: Could not open video {video_path}")

    exit()

  

frame_width = int(cap.get(cv2.CAP_PROP_FRAME_WIDTH))

frame_height = int(cap.get(cv2.CAP_PROP_FRAME_HEIGHT))

fps = int(cap.get(cv2.CAP_PROP_FPS))

  

output_path = "segmented_output.mp4"  

fourcc = cv2.VideoWriter_fourcc(*'mp4v')

out = cv2.VideoWriter(output_path, fourcc, fps, (frame_width, frame_height))

  

while cap.isOpened():

    success, frame = cap.read()

    if success:

        results = model(frame)

  

        annotated_frame = results[0].plot()

  
  

        out.write(annotated_frame)

  

        cv2.imshow("YOLOv8 Segmentation", annotated_frame)

  

        if cv2.waitKey(1) & 0xFF == ord('q'):

            break

    else:

        break  

  
  

cap.release()

out.release()

cv2.destroyAllWindows()

  

print(f"Video saved to {output_path}")
```




