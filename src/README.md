# Code Repository of Our Proposed Pipeline
Each directory represents a stage in our execution pipeline.
We used the PlotQA dataset that is available at their [GitHub Repository](https://github.com/NiteshMethani/PlotQA/blob/master/PlotQA_Dataset.md).

## Stage 1: Classification Of Chart Images by Type using VGG-16 Model
To accomplish chart type classification, we trained a VGG-16 model on a subset of 5000 images chosen at random from the training dataset.
We generated a balanced version of this training subset and an unbalanced version as well.
In order to comparatively analyse the effect of balanced or unbalanced classes in the training subset we used a test subset that comprised of 1000 images. These test images were chosen at random from the PlotQA testing dataset. 
We also included some types of charts that were not part of the PlotQA dataset (such as spatial map, heatmap and pie chart) just to observe the shortcomings of the model. 
Upon examining the performance of both the models (one trained on a balanced subset of images and another on an unbalanced subset) we observed that the model trained on balanced subset was better in terms of accuracy but by a very narrow margin.
Source Code and Results are placed in their respective folders in the repository.