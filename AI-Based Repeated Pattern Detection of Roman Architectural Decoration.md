---
tags:
  - school-project
  - masters-thesis
  - pattern-detection
  - machine-learning
  - artificial-intelligence
  - computer-vision
  - programming
  - solo-project

programming-language: Python
layout: project
title: "AI-Based Repeated Pattern Detection of Roman Architectural Decoration"
permalink: projects/masters-thesis/
---

For my master’s thesis, I developed an AI-based system to detect and segment repetitive decorative patterns in Roman architectural elements, with a focus on the ancient region of Asia Minor. The project combined computer vision techniques with archaeological research, bridging my dual interests in artificial intelligence and history.  
This thesis was conducted in collaboration with Julie Verlinden, a PhD researcher in ancient archaeology, who provided the raw image dataset and key archaeological insights through relevant literature.  
The project was an internal thesis hosted at KU Leuven, Campus De Nayer. Since the campus was over 100 km away, most of the work was carried out remotely. We coordinated progress through regular Microsoft Teams meetings, typically held every few weeks.

## Objectives

1. Automate the detection of repeating decorative patterns using computer vision and artificial intelligence.
2. Contribute to historical research by analyzing pattern similarities across time and space.
3. Reduce manual labor in archaeological documentation by creating an efficient recognition pipeline.

## Features and Methodology

1. **Dataset Creation**:
   - Composed a dataset of ~900 images from archaeological sites, supplemented by literature sources.
   - Focused on close-up photos of architectural patterns (e.g., bead-and-reel, egg-and-dart).
2. **Algorithm Optimization**:
   - Implemented and enhanced two AI models: 
     - "Unsupervised Semantic Discovery Through Visual Patterns Detection."
     - "Repeated Pattern Detection Using CNN Activations."
   - Combined the strengths of both algorithms in a custom pipeline.
   - Added preprocessing and did hyperparameter optimization.  
3. **Pattern Segmentation**:
   - Accurately segmented horizontal patterns into individual units for further classification.
   - Addressed challenges like under- and over-segmentation through preprocessing techniques (e.g., filtering, contrast enhancement).

## Results
 - Demonstrated successful detection and segmentation of several pattern types with varying degrees of accuracy.
 - Highlighted areas for improvement, including more robust handling of complex or degraded patterns.
  
<img src="/assets/eindfoto2_DSC_0562 2023-10-02.png" alt="screenshot of end result" width="screen-width" >
> An example of the end result image after the pipeline.

## Conclusion

This research provided a solid foundation for further exploration of pattern classification and cross-regional comparisons in Roman architecture. While refinement is needed to enhance segmentation consistency, the project successfully bridged AI and historical studies, paving the way for future interdisciplinary research.

**Repository**: [GitHub - Pattern Detection](https://github.com/duster3000/pattern-detection-roman-architecture)  
[Thesis text](https://1drv.ms/b/c/f8cdfc1d73dd7ec2/EQ3DHHoqkJBOksVw-NIGY30BdCXc80pnfua1T4WU6sg1Nw?e=3FBJbE)  

---

*Technologies used*: Python, OpenCV, Scikit-image, Pytorch  
*Project supervisor*: Toon Goedemé  
*Time range*: September 2023 – June 2024  
*Rating*: 3.5/5  


