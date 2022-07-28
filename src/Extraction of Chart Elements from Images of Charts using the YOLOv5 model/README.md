# Stage 2: Extraction of Chart Elements from Images of Charts using the YOLOv5 model

We used a modified version of the pre-trained YOLOv5 model to predict bounding boxes for various chart elements in chart images such as dots for dot plots, lines for line charts, and bars for bar charts.

We wrote a script to fetch the required annotations (bounding box coordinates) of various chart elements for the images in the training set. Since YOLOv5 uses a normalized coordinate system, we had to convert the annotations concerning each image since the images vary in size.

We performed the following experiments while training the model:
- Used a balanced set consisting equal proportion of images across all chart types.
- Used an unbalanced set where the number of chart images of a chart type as per the original proportion in the PlotQA dataset.
- Used both, the balanced and unbalanced sets, to train the model at an IoU value of 0.5 (commonly used for object detection tasks).
- Used both the balanced and unbalanced sets to train the model at an IoU value of 0.9 (as recommended by past researchers for best accuracy).

We generated a precision vs recall curve and confusion matrix for all the above-mentioned experimental scenarios to comparatively analyze the best performing conditions for extracting chart elements.

We also tested the performance of our models on a test set consisting of chart images from the PlotQA dataset and some natural images to visually inspect the bounding boxes predicted by the models.

All experimental models' source code is placed in the source code subdirectory.

The evaluation metrics for all the experimental models and the test set images (with predicted bounding boxes drawn on them) are placed in the Results subdirectory.