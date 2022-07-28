## Stage 1: Classification Of Chart Images by Type using VGG-16 Model

To accomplish chart type classification, we trained a VGG-16 model on a subset of 5000 images chosen at random from the training dataset.

We generated a balanced version of this training subset and an unbalanced version.

In order to comparatively analyze the effect of balanced or unbalanced classes in the training subset, we used a test subset that comprised 1000 images. These test images were chosen at random from the PlotQA testing dataset.

We also included some types of charts that were not part of the PlotQA dataset (such as spatial maps, heatmap, and pie charts) just to observe the model's shortcomings. 

Upon examining the performance of both the models (one trained on a balanced subset of images and another on an unbalanced subset) we observed that the model trained on a balanced subset was better in terms of accuracy but by a very narrow margin.

Source Code and Results are placed in their respective subdirectories.