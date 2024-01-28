# 📸 Image Segmentation with YoLo Model 🚀

Welcome to our repository! Here, we're all about image segmentation. Our star player is the `image_segmentation.ipynb` file, a Jupyter notebook that uses the YoLo model to perform image segmentation on a set of input images. 🖼️

## 📁 File Structure

Here's a quick rundown of what you'll find in `image_segmentation.ipynb`:

1. **Import Necessary Libraries**: This section imports the necessary libraries for the image segmentation task. 📚
2. **Load the trained YoLo Model weights**: Here, we load the trained YoLo model weights from a file named "best.pt". 🏋️
3. **Select the folder where input and output images are stored**: This section defines the directories for the input images and the output results. 🗂️
4. **Load the input images and perform detection**: This section reads each image from the input directory, performs object detection using the YoLo model, and saves the results in the output directory. 🕵️

## 📚 Dependencies

This file relies on the following external libraries:

1. **ultralytics**: A library for the YoLo model. 🚀
2. **cv2**: OpenCV library for image processing. 📸
3. **os**: Standard Python library for OS related operations. 💻

## 🚀 Usage Examples

Here's a quick example of how to use the YoLo model for object detection on an image:

```python
from ultralytics import YOLO
import cv2
import os

model = YOLO("best.pt")
input_folder = "input_images"
output_folder = "Results"

for filename in os.listdir(input_folder):
    input_image_path = os.path.join(input_folder, filename)
    image = cv2.imread(input_image_path)
    results_image = model(
        image,
        save=True,
        project=output_folder,
        name=os.path.splitext(filename)[0],
        boxes=False,
        show_labels=False,
    )
```

## 📝 Notes

The results of the object detection are saved in the output directory without bounding boxes or labels. The filename of each input image is used as the name for the corresponding result.

So, what are you waiting for? Let's get segmenting! 🎉