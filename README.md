# PneumoniaDetection
A comprehensive empirical study revealing why complex generative models underperform simple augmentation in medical imaging, with quantitative analysis and clinical insights.

## Abstract
This repository contains the implementation and analysis of five different approaches to pneumonia detection from chest X-rays, systematically comparing traditional methods against CycleGAN-based techniques. Our key finding: simple traditional augmentation achieves 99.2% sensitivity and 0.993 AUROC, while CycleGAN variants fail catastrophically with AUROC ranging from 0.53 to 0.65, despite being orders of magnitude more complex.
Through systematic analysis using GradCAM visualization, intensity distribution studies, and regional change mapping, we identify the exact mechanisms of GAN failure in medical imaging, providing crucial guidance for practitioners.

## Key Contributions
- Rigorous empirical comparison of 5 models: Baseline ResNet50, Traditional Augmentation, CycleGAN Augmentation, and two CycleGAN Anomaly Detection variants
- Quantitative evidence that intensity preservation matters more than visual realism in medical imaging
- Complete reproducible pipeline with trained models and comprehensive visualization tools
- Valuable negative results documenting when generative models should not be used

## Key Findings for Practitioners
- Warning: CycleGAN and similar generative models should not be used for medical image augmentation without diagnostic-aware constraints.
- Recommendation: Traditional augmentation techniques (rotation, translation, zoom, shear) preserve diagnostic features more effectively than generative approaches.
- Clinical Insight: In pneumonia detection, preserving intensity distributions and lung field textures is more important than generating visually diverse synthetic images.
