# Extracting Information from Images of Charts

## Research Question

 _Can existing state-of-the-art object detection algorithms produce efficient results to extract information from images of scientific charts that are arguably different from natural images?_

## Summary

Our work in this project can be summarised as follows:
- We highlight the complexity and significance of extracting information from images of scientific plots. 
- We extensively review published literature by past researchers to understand their conducted work and contribution to the field. 
- After comparing some published VQA datasets based on chart images, we decided to use the PlotQA dataset. 
- Our intricate exploratory analysis of the PlotQA dataset reveals a discrepancy in their ground-truth bounding boxes for chart titles in their images.
- We propose an execution pipeline to accomplish three tasks that are essential to extract information from images of scientific plots: 
    - **Classification of chart images by chart type**
    - **Extraction of chart elements from chart images**
    - **Extraction of Textual Chart Components embedded in  chart images**.
- We use modified versions of two object detection models, VGG16 and YOLOv5, at various stages of our pipeline. We also performe experimental analysis based on different subsets (balanced and unbalanced) to observe the effect on the final model’s prediction.

## Repository Overview

- The code and results for each stage in our proposed pipeline is organised as individual subdirectories in the `src` sub-directory
- We created explanatory documents to outline the structure of the PlotQA dataset. These documents are present in the `docs/documentation` sub-directory
