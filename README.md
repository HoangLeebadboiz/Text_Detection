# TEXT DETECTION MODELS USING YOLO11

This is project for Text Dectection using Ultralytics API to pretrain model yolo11-obb

## MODELS

1. `yolo11n-obb`
2. `yolo11l-obb`

### One Class Detection

1. Model n: [Model-n](./Models_One_Class/Model_n/best.pt)
2. Model l: [Model-l](./Models_One_Class/Model_l/best.pt)

### Multiple Classes Detection

This feature uses model `yolo11l-obb` for OBB Object Detection

Link: [Model](./Models_Multiple_Classes/best.pt)

### Download packages

``` bash
pip install ultralytics
```

### Train model

``` python
from ultralytics import YOLO

# Load a model
model = YOLO("./Models_One_Class/Model_l/last.pt")  # load an custom model

# Train the model
results = model.train(data="data.yaml", epochs=200, imgsz=640)
```

### Inference

``` python
# Inference
predict = model.predict("./Data/") # Load Image path or folder image path

# Show bbox
for result in predict:
    result.show(labels=True)
    result.save()
```

### Results

![Result]("./Results/result.png)
