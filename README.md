# Intelligent-Forecasting-for-Solar-Flares

## Project Overview  
This project conducts intelligent prediction research on solar flares based on magnetogram data from SDO/SHARP, SDO/HMI, and ASO-S/FMG. By integrating multi-source solar magnetosphere observation data, it constructs efficient machine learning/deep learning models to achieve advance prediction of solar flare occurrence probability and intensity, providing technical support for space weather early warning.  


## Research Background  
- **Impact of Solar Flares**: Solar flares are intense energy release phenomena in the solar atmosphere, which can trigger geomagnetic storms, ionospheric disturbances, etc., posing serious threats to satellite communications, power systems, and aerospace activities.  
- **Prediction Challenges**: Traditional physical models rely on complex magnetohydrodynamic calculations with insufficient real-time performance; the nonlinear characteristics of solar magnetic field evolution pose higher requirements for data-driven intelligent prediction methods.  
- **Data Advantages**: High-resolution magnetogram data provided by detectors such as SDO and ASO-S lay a foundation for capturing the fine structure and evolution laws of the solar magnetic field.  


## Data Sources  
### Description of Multi-source Magnetogram Data  

| Data Source       | Mission        | Data Type       | Temporal Resolution |  
|-------------------|----------------|-----------------|---------------------|  
| SDO/SHARP         | SDO            | Line-of-sight magnetogram | 12 minutes          |  
| SDO/HMI           | SDO            | Line-of-sight magnetogram | 12 minutes          |  
| ASO-S/FMG         | ASO-S          | Line-of-sight magnetogram | 2 minutes           |  

### Data Processing Workflow  
- **Preprocessing**: Denoising, calibration, and coordinate unification.  
- **Label Construction**: Flares are labeled by grades (C, M, X) based on X-ray flux data from GOES satellites.  


## Methodological Framework  
### Model Architecture  
1. **Spatio-temporal Model**:  
   - Spatial dimension: Fuse high-resolution details of magnetograms.  
   - Temporal dimension: Construct magnetogram sequences with multi-time windows (1-24 hours prior).  
2. **Deep Learning Model**:  
   - Backbone network: 3D convolutional neural network、Transformer (captures spatio-temporal features).  
   - Attention mechanism: Focuses on key regions such as magnetic neutral lines and strong gradient areas.  

### Key Technologies  
- Imbalanced data processing: Adopts weighted cross-entropy loss function.  
- Real-time prediction optimization: Model inference time <10 seconds/sample (accelerated by GPU).  
- Uncertainty quantification: Outputs prediction probability distributions and confidence intervals.  


## Main Achievements  
1. **Prediction Performance**:  
   - Achieves performance comparable to flare prediction models on the CCMC platform.  
   - Low miss rate for X-class flares (compared to traditional methods).  
2. **Model Advantages**:  
   - Interpretability: Visualizes contributions of key magnetic structures via Grad-CAM.  
   - Generalization ability: Successfully validated with data from the 2023-2024 solar activity period.  
3. **Publications**:  
   - The research results are published in *The Astrophysical Journal Supplement Series*:  
     \item [DOI: 10.3847/1538-4365/add149](https://doi.org/10.3847/1538-4365/add149)  


## Future Work  
- Integrate more data sources: Solar wind parameters, coronal imaging data.  
- Improve prediction timeliness: Attempt to develop models for 48-72 hours advance prediction.  
- Incorporate physical quantities such as magnetic helicity and free energy as auxiliary features, and introduce magnetic reconnection theory to constrain model training objectives.
