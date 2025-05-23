# Model-trained-for-drought-prediction
Overview:
  This project presents a multi-modal deep learning architecture for predicting hydrological droughts using satellite imagery, environmental time-series data, and contextual tabular features. The      model leverages Spatio-Temporal Graph Convolutional Networks (STGCNs) to capture both spatial dependencies and temporal dynamics across interconnected regions.
  
Highlights:
  Combines satellite imagery (RGB/NIR), time-series climate indicators (temperature, rainfall, NDVI), and tabular data (soil type, land use).
  Designed to handle class imbalance with weighted loss functions and data augmentation.
  Uses STGCN architecture to capture spatio-temporal interactions for drought prediction.
  Offers explainability via saliency maps, SHAP values, and attention heatmaps.
  
Dataset:
  Image Count: 5,110 (28x28, RGB/NIR)
  Drought Class: 4.9%
  Time-Series Features: Temperature, rainfall, NDVI, soil moisture, humidity
  Tabular Features: Land use, elevation, soil type
  Source: MODIS, Sentinel-2, meteorological stations (public data only)

Model Architecture:
  +----------------+     +-------------------+     +----------------------+
| Satellite CNN  | --> | Feature Vector     |     |                      |
+----------------+     +-------------------+     |                      |
                                                   --> Fusion --> STGCN --> Output
+----------------+     +-------------------+     |                      |
| Tabular FNN    | --> | Feature Vector     |     |                      |
+----------------+     +-------------------+     +----------------------+

Requirements:
  Python 3.9+
  TensorFlow 2.x
  NumPy, Pandas, Scikit-learn
  NetworkX, Matplotlib, Seaborn, GeoPandas
