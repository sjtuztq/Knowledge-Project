# Notes: Spatially Supervised RCNN for Visual Object Tracking
![](https://img.shields.io/badge/status-Under_construction-orange.svg?style=flat-square)

## Paper infomation
Citation 26

## Problem addressed / Motivation
 - Visual tracking : 
    - **Deformation**
        - target deformations
        - object deformation
    - **Scale**
        - scale changes
    - **Illumination**
        - illumination variations
    - **Motion**
        - fast and abrupt motion
        - motion blur
    - **partial occlusions**
    - **background clutters**
 - Motivation
    - Tracking failures can often be recovered by analysing
        1. historical visual semantics
        2. historical tracking proposals
    

## Related work
### Normal methods
 - Tracking by detection
    - Complicated system
    - Detection become bottleneck
 - Appearance-based tracking methods
    - Adopt generative or discriminative models to separate foreground from bg
    - Low level hand crafted features
        - No semantic info 
        - Not robust
        - Limited discriminative power
 - Karman filter based
    - Temporal based
    - Only consider location history 
### Closely related
 - Object tracking using RNN
    - Use RNN as an attention scheme to spacially glimpse on different reagions
    - Use traditional binary classifier at local regions 

## Idea / Observation / Contribution
### Observation
How to **extend DNN analysis to the spacio-temporal** domain for object tracking has not been adequately studied
### Contribution
1. **Model:** Introduce a modular network
    - Insight into model design and training
    - LSTM interpretation and regression capabilities of high level visual features
2. **Idea:** Extend detection to spatio-temporal domain
    - Before: ConvNet-based tracker, only spacial domain
3. **Performance:** Accurate and efficient with low complexity


## Implementation
## Formulation / Solver / Implementation
- TODO
- Utilize VGG16 model for convolutional layers (conv1 and conv5) in FCN.
- Follow faster rcnn for the pedestrian proposal network
- From pedestrian proposals, we apply three fully connection layers (fc6-8) to generate final feature for person re-id

## Useful info / tips
- TODO
- If the softmax target is very sparse and the minibatch contains only a few label classes, the gradients would be biased on these classes at each SGD iteration
- It is observed that detectors greatly affect the person search performance of baseline method and there is still a big gap between using the ground truth bounding boxes and the automatically detected ones.

# Evaluation
## Dataset
- TODO
- Own dataset (E2E Person Search)
- There are two parts in the dataset: street snaps and movies.
- Low-resolution subset and occlusion subset

## Metrics
- TODO
- designed different evaluation protocols by setting the gallery size to 50, 100, 500, 1, 000, 2, 000, and 4, 000
- meanAveraged Precision (mAP): A candidate window is considered as positive if its overlap with the ground truth is larger than 0.5
- top-k matching rate on bounding boxes: A matching is counted if a bounding box among the top-k predicted boxes overlaps with the ground truth larger than the threshold

## Results
- TODO
- Baseline detector: ACF + Deep detector
- Baseline re-id methods: BoW with cosine distance, DenseSift+ColorHist with Euclidean and KISSME distance metric, IDNet

# Resource
## Project page
- TODO
http://www.ee.cuhk.edu.hk/~xgwang/PS/dataset.html

## Source code
- TODO
https://github.com/ShuangLI59/person_search

## Dataset
- TODO
Need to send request
https://drive.google.com/open?id=0B-GOvBat1maOVUE3WmNNUVRGamc

## Other paper reading notes

## Others

# Questions
- TODO
- How to perform re-id algorithm in current framework?

# Build upon
- TODO
- Performance is low on low-resolution images
- Extend to video data (plus tracking)

# Paper connections

- Faster RCNN
