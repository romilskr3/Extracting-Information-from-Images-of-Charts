# Stage 3: Text Extraction from Chart Images using Tesseract OCR

We used a modified version of the pre-trained YOLOv5 model to predict bounding boxes for the following textual chart elements in chart images:
1. Chart Title
2. X-Axis Label
3. Y-Axis Label
4. Legend Elements

We wrote a script to fetch the required annotations (bounding box coordinates) of above mentioned textual chart elements for the images in the training set. Since YOLOv5 uses a normalized coordinate system, we had to convert the annotations concerning each image since the images vary in size.

Upon completion of training, we compiled a test set of chart images and parsed it to the trained model. The model generated bounding box predictions for these images.

We used these predicted bounding boxes and the images in the test set to extract text elements in the chart images using Tesseract OCR. We cropped the textual chart elements to their predicted bounding boxes, converted them into binary images and corrected the orientation, if required, before parsing it to the OCR module for text extraction.

We built a compilation script that used this extracted text from the OCR and predicted class labels from the YOLOv5 model to assemble a dictionary format of the test set images. This dictionary can be exported as a JSON file.

The source code and results are placed in their respective subdirectories.