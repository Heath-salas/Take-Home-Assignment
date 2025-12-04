# Take-Home-Assignment

The script looks through a set of 10 images and performs:

1. YOLOv8 Object Detection
Model: yolov8m.pt (Ultralytics)

For each image:
- Runs YOLO detection
- Records inference time (in milliseconds)
- Extracts:
  - All detected object labels
  - Confidence score per object
- Computes average YOLO confidence for that image

2. Faster R-CNN Object Detection
Model: fasterrcnn_resnet50_fpn (Torchvision)

For each image:
- Runs Faster R-CNN detection
- Records inference time (in milliseconds)
- Extracts:
  - All detected object labels
  - Confidence score per object (scores ≥ 0.5)
- Computes average Faster R-CNN confidence for that image

3. Image-Level Classical CV Metrics
Sharpness Score (Laplacian Variance)

  - Measures the level of detail/blur in the image
    - Higher = sharper
    - Lower = blurrier

  - cv2.Laplacian(img, cv2.CV_64F).var()

Dominant Colors (KMeans Clustering)

  - Extracts the top 3 dominant RGB colors from the image using KMeans.

