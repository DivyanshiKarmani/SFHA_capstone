# A memory-efficient Machine Learning pipeline for classification of Mass Spectrometry data - Model Card

## Model Overview
This project builds a machine learning model to classify mass spectrometry scans based on BSA concentration (0, 5, 50). The goal is to evaluate whether engineered spectral features can capture meaningful differences between experimental conditions.

## Intended Use
- Exploring feature engineering and classification on large-scale LC-MS biological datasets.
- Not intended for clinical or production use.

## Data
- Input: Mass spectrometry scan-level data (~12M rows per file)
- Features engineered via aggregation (mean m/z, intensity stats, peak count, etc.)
- Labels: BSA concentration (0, 5, 50).

## Model Details
- Input: Mass spectrometry scan-level data (~12M rows per file)
- Features engineered via aggregation (mean m/z, intensity stats, peak count, etc.)
- Labels: BSA concentration (0, 5, 50).

## Performance
- Test Accuracy: ~0.57
- Cross-validation Accuracy: ~0.45 ± 0.02
Performance indicates moderate predictive power, suggesting partial separability of classes.

## Key Insights
- Tree-based models outperform linear models → relationships are non-linear.
- Features like retention time and precursor m/z are most informative.
- Some class confusion remains, especially for higher BSA concentrations.

## Limitations
- Model does not directly detect chimeric spectra.
- Moderate accuracy suggests incomplete feature representation.
- High computational cost due to large dataset.
- Limited hyperparameter search due to memory constraints.

## Future Work
- Add domain-specific features (e.g., fragmentation patterns, spectral entropy).
- Try more advanced models (e.g., XGBoost, LightGBM).
- Improve labeling strategy for true chimeric spectra detection.
