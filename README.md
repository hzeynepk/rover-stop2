# rover-stop2
an improved version of rover-stop

# Stop Sign Detection with YOLOv8

This project trains a YOLOv8 model to detect stop signs using a custom dataset from Roboflow.

## Steps
1. Install dependencies
   ```bash
   # Pip install method (recommended)

!pip install ultralytics==8.2.103 -q

from IPython import display
display.clear_output()

# prevent ultralytics from tracking your activity
!yolo settings sync=False

import ultralytics
ultralytics.checks()
2.	Download dataset from Roboflow using your API key
```bash
!pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="apikey")
project = rf.workspace("karn-efr8f").project("stop-sign-b3mbf")
version = project.version(1)
dataset = version.download("yolov8")
3.	Train model
	```bash
   model.train(data="/content/Stop-sign-1/data.yaml", epochs=20, batch=16, imgsz=640)
4.	Validate model
   ```bash
   metrics = model.val()
5.	Run predictions
   ```bash
   results = model.predict(source="test/images", conf=0.25)
