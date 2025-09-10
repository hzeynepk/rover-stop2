# rover-stop2
An improved version of rover-stop

 Steps

### 1. Install dependencies
```bash
# Pip install method (recommended)
pip install ultralytics==8.2.103 -q

# Prevent ultralytics from tracking your activity
yolo settings sync=False

from IPython import display
import ultralytics

display.clear_output()
ultralytics.checks()
---

2. Download dataset from Roboflow

pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="YOUR_API_KEY")
project = rf.workspace("karn-efr8f").project("stop-sign-b3mbf")
version = project.version(1)
dataset = version.download("yolov8")

3. Train model

from ultralytics import YOLO

model = YOLO("yolov8n.pt")
model.train(data="/content/Stop-sign-1/data.yaml", epochs=20, batch=16, imgsz=640)

4. Validate model

metrics = model.val()

5. Run predictions

results = model.predict(source="test/images", conf=0.25)

---

👉 Böylece hem **bash** (terminal komutları) hem de **python** blokları doğru şekilde ayrılır.  

İstiyor musun ben bunu senin repo’daki `README.md` dosyana uyacak şekilde sadeleştirilmiş kısa versiyonunu da hazırlayayım?
