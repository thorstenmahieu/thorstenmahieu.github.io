---
tags:
  - school-project
  - masters-thesis
  - pattern-recognition
  - machine-learning
  - artificial-intelligence
  - computer-vision
  - programming

programming-language: python
layout: page
title: "AI-Based Pattern Recognition of Roman Architectural Decoration"
permalink: projects/masters-thesis/
---
{::comment} # AI-Based Pattern Recognition of Roman Architectural Decoration {:/comment}

For my master’s thesis, I developed an AI-based system for recognizing and segmenting repetitive decorative patterns in Roman architectural elements, focusing on the ancient region of Asia Minor. This project was carried out in close collaboration with Julie Verlinden, a PhD student in ancient archaeology, who provided the raw image dataset and relevant archaeological literature.


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

---

*Skills learned*: Computer vision, research, repeated pattern detection  
*Project supervisor*: Toon Goedemé  
*Time range*: September 2023 – June 2024  
*Rating*: 3.5/5
Back to [projects](projects.md)
