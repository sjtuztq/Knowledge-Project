# Notes: Spatially Supervised RCNN for Visual Object Tracking
![](https://img.shields.io/badge/citation-26-green.svg?style=flat-square)
![](https://img.shields.io/badge/keyword-Visual_Object_Tracking-green.svg?style=flat-square)

![](https://img.shields.io/badge/Author_citation-40-blue.svg?style=flat-square)
![](https://img.shields.io/badge/Author-Guanghan_Ning:Ph.D.Candidate-blue.svg?style=flat-square)
![](https://img.shields.io/badge/Univ-University_of_Missouri_Columbia-blue.svg?style=flat-square)

##  Resource
Project page with source code available [[1]]

Source code available on github page [[2]]

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
### System overview
- YOLO: Object detection
    - `Assignment cost matrix`: IOU between current detection and short-term history of validated detections
    - First frame is determined by IOU between detections and GT
    - Threshold for minimum IOU

- E2E pipeline
    - CNN
        - Input: video frame
        - Output: 4096 dim feature vector
    - YOLO
        - Input: 4096 dim feature vector
        - Output: S * S * (B * 5 + C)
        - B<sub>t</sub> = (0, x, y, w, h, 0), since no classification is needed
    - LSTM-RNN
        - Input: 4096 dim feature vector + B<sub>t,i</sub> + S<sub>t-1</sub>
        - Loss: MSE loss for B
        - Optimizer: Adam
    - (Alternative) Heat map
        - Convert ROLO location to 32x32 bitmap
        - Loss: MSE

## Useful info / tips
 - It seems that history would be useful in supervising LSTM to restrict prediction to a specific range

## Experiments
### Dataset
 - Benchmark:`OTB` dataset from paper _Object tracking benchmark_ (same author)
 - OTB30: 30 videos from the benchmark
 - YOLO training: pretrain on `ImageNet` and finetune on `VOC`
### Qualitative results
 - Tracking is generalized to unseen objects (trivial)
 - LSTM can interpret the visual features
 - LSTM is capable of regressing `visual features` + `location history` to `regiion inference`
 - Able to handle occlusion
### Quantitative results
 - Evaluation: `Temporal Robustness Evaluation` ,`Spacial Robustness Evaluation`, and `Average Overlap Scores`
 - Baseline: CNN-SVM
 - Training on 22 videos in OTB30 testing on 8 videos in OTB30
 - Training on 1/3 frames in OTB30 testing on whole sequence
 - Training with 1/3 gt and all sequence frames (How?)


## Other paper reading notes

## Questions
- What does `dynamics` mean in 4.3
- What does `an online appearance model` mean in section 3.4 and 4.1
    - My answer:
        - Online: it uses location history and keeps updating
        - Appearance model: it predicts the location(appearance) of the target
- (YOLO) What happens if multiple known classses are in the same video?
    - output the most confident one?
- How does YOLO distinguish between 2 people if it's only trained to understand the features of generic human? Why in Figure 6 (section 4.2) it tracks only one person? 
- How to track designated target?
- How does YOLO predict for the first frame, if no GT is provided?
- How to, if possible, quickly extend the network(YOLO part) to detect new class?
- Details about heatmap


# Build upon
- Track arbitrary object that is annotated?
- Use semantic segmentation instead of YOLO? (occlusion)
- Dramatic drop in blury cases (`OAB`, `CNN-SVM`, `STR UCK` are much better) performance is poor (refer to paper table1)
- Tracking multiple instances / classes ?

# Paper connections
- YOLO[[3]]

## Reference
[[1]] Recurrent YOLO for object tracking

[[2]] Github: Guanghan/ROLO

[[3]] Redmon, J., Divvala, S., Girshick, R., & Farhadi, A. (2015). You Only Look Once: Unified, Real-Time Object Detection. CVPR 2016


[1]: http://guanghan.info/projects/ROLO/ "Project page"
[2]: https://github.com/Guanghan/ROLO
[3]: https://arxiv.org/abs/1506.02640
