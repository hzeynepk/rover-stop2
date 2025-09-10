# rover-stop2
an improved version of rover-stop

# Stop Sign Detection with YOLOv8

This project trains a YOLOv8 model to detect stop signs using a custom dataset from Roboflow.

## Steps
1. Install dependencies
   ```bash
   pip install ultralytics roboflow

2.	Download dataset from Roboflow using your API key
3.	Train model
   model.train(data="/content/Stop-sign-1/data.yaml", epochs=20, batch=16, imgsz=640)
4.	Validate model
   metrics = model.val()
5.	Run predictions
   results = model.predict(source="test/images", conf=0.25)
