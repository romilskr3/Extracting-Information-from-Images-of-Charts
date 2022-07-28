# Code Repository of Our Proposed Pipeline
Each subdirectory represents a stage in our execution pipeline.
We used the PlotQA dataset that is available at their [GitHub Repository](https://github.com/NiteshMethani/PlotQA/blob/master/PlotQA_Dataset.md).

## Stage 1: Classification Of Chart Images by Type using VGG-16 Model

To accomplish chart type classification, we trained a VGG-16 model on a subset of 5000 images chosen at random from the training dataset.

We generated a balanced version of this training subset and an unbalanced version as well.

In order to comparatively analyse the effect of balanced or unbalanced classes in the training subset we used a test subset that comprised of 1000 images. These test images were chosen at random from the PlotQA testing dataset.

We also included some types of charts that were not part of the PlotQA dataset (such as spatial map, heatmap and pie chart) just to observe the shortcomings of the model. 

Upon examining the performance of both the models (one trained on a balanced subset of images and another on an unbalanced subset) we observed that the model trained on balanced subset was better in terms of accuracy but by a very narrow margin.

Source Code and Results are placed in their respective subdirectories.

## Stage 2: Extraction of Chart Elements from Images of Charts

We used a modified version of the pretrained YOLOv5 model to predict bounding boxes for various chart elements in chart images such as dots for dot plots, lines for line chart and bars for bar charts.

We wrote a script to fetch the required annotations (bounding box coordinates) of various chart elements of the training set. Since YOLOv5 uses a normalized coordinate system, we had to convert the annotations with respect to each image since the images vary in size.

We performed the following experiments while training the model:
- Used a balanced set consisting equal proportion of images across all chart types.
- Used an unbalanced set where the number of chart images of a chart type was in accordnace with the original proportion in the PlotQA dataset.
- Used both the balanced and unbalanced sets to train the model at an IoU value of 0.5 (which is commonly used for object detection tasks).
- Used both the balanced and unbalanced sets to train the model at an IoU value of 0.9 (as recommended by past reaserchers for best accuracy).

We generated precision vs recall curve and confusion matrix for all the above mentioned experimental scenarios to comparitively analyse the best performing conditions for extracting chart elements.

We also tested the performance of our models on a test set consisting of chart images from the PlotQA dataset and some natural images to visually inspect the bounding boxes predicted by the models.

The source code of all the experimental models in placed in the source code subdirectory.

The evaluation metrices for all the experimental models and the test set images (with predicted bounding boxes drawn on them) are placed in the Results subdirectory.