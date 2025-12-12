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

## Repo Structure
PneumoniaDetection/
├── models/
│   ├── model1_baseline/          # Baseline ResNet50 implementation
│   ├── model2_traditional_aug/   # Traditional augmentation pipeline
│   ├── model3_cyclegan_aug/      # CycleGAN augmentation approach
│   ├── model4_identity_anomaly/  # Normal-Normal CycleGAN for anomaly detection
│   └── model5_cross_domain/      # Normal-Pneumonia CycleGAN translation
├── analysis/
│   ├── intensity_distribution/   # Distribution shift quantification
│   ├── gradcam_visualization/    # Attention mechanism analysis
│   └── regional_changes/         # Anatomical modification mapping
├── results/
│   ├── performance_metrics.csv
│   ├── confusion_matrices/
│   ├── roc_curves/
│   └── clinical_interpretation/
├── data/
│   └── preprocessing/            # CLAHE and artifact removal pipeline
└── notebooks/
    ├── 01_data_exploration.ipynb
    ├── 02_model_training.ipynb
    ├── 03_failure_analysis.ipynb
    └── 04_clinical_validation.ipynb
