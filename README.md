# Object Detection Project

This repository demonstrates how to perform object detection using the pre-trained YOLOv5 model. It allows you to input images from a local file path or a URL, perform inference to detect objects, and display the results with bounding boxes, labels, and confidence scores.

#Features

1.) Uses the pre-trained YOLOv5 model for object detection.

2.) Accepts images from both URLs and local file paths.

3.) Displays the original image and the image with detected objects in Google Colab.

4.) Outputs detected object labels, confidence scores, and bounding box coordinates.

#Requirements

To run the code, the following libraries are required:

-> torch (for loading and running the YOLOv5 model)

-> cv2 (OpenCV for image processing and display)

-> numpy (for array manipulation)

-> requests (for loading images from URLs)

-> Pillow (for image handling)

-> google.colab.patches (for displaying images in Google Colab)


#You can install the required packages using the following:

-> !pip install torch torchvision opencv-python pillow requests


# Usage

1.) Load the YOLOv5 Model: The code loads the pre-trained yolov5s model from the Ultralytics YOLOv5 hub.

-> model = torch.hub.load('ultralytics/yolov5', 'yolov5s', pretrained=True)


2.) Input an Image: The user can input the path of a local image or the URL of an image for object detection. The image will be loaded using OpenCV (for local files) or requests and Pillow (for URLs).

-> image_source = input("Please enter the path or URL of the image: ")


3.) Inference and Results: After loading the image, the code runs object detection and displays the results (detected objects with bounding boxes, labels, and confidence scores).

-> results = model(img_rgb)
   print(results.pandas().xyxy[0])  # Display detection results as a DataFrame


4.) Visualize Results: The image with bounding boxes drawn around detected objects is displayed in the Google Colab environment.

-> results_img = results.render()[0]
   display_image(results_img)

   
5.) Exiting the Program: To exit the loop, type quit when prompted for an image.

-> Please enter the path or URL of the image (or type 'quit' to exit): https://example.com/image.jpg


# The model will display the image, detect objects, and print the results in the following format:

Label: person 

Confidence: 0.87 

Bounding Box: [xmin, ymin, xmax, ymax] 


# Notes

-> This code is optimized for Google Colab, where it uses the cv2_imshow function for image display.

-> YOLOv5 is a powerful object detection model that can be used for a wide variety of applications such as surveillance, autonomous driving, and more.
