# Predicting Cell Cycle Phase from Embryonic Mice Stem Cell Gene Expression Data using Circular Regression with Deep Learning

In the field of biological research, the use of advanced technologies, such as deep learning, has greatly improved our ability to understand complex cellular processes. This study, combining computational biology and cell cycle dynamics, aims to simplify the prediction of cell cycle phases and identify important genes involved. We introduce a new deep learning algorithm, called MultipleCircularRegression, designed specifically for predicting cell cycle phases using raw gene expression data from embryonic mice stem cells. The model effectively captures the cyclical patterns using three connected layers and dropout units for better generalization. Over 800 training cycles, the algorithm consistently reduces cyclic loss, indicating robust learning. Evaluation metrics (MAE = 0.0718, RMSE = 0.1321, R-squared = 0.7779) confirm the model's accuracy in predicting cell cycle phases. By using Captum permutation for feature selection, we identify the top 20 influential genes (e.g., Plk1, Ube2c) and visualize their periodic patterns. This research not only provides a powerful method for predicting cell cycle phases but also highlights the key genes involved in orchestrating these biological processes.

## Data availability
This project utilizes mouse embryonic stem cell (mESCs) data annotated with the cell cycle phase obtained from the Zenodo repository  <a href="https://doi.org/10.5281/zenodo.4719436">![ZenodoDOI](zenodo.4719436.svg)</a>. The specific dataset can be retrieved using the following command: 

```bash
curl -LJO https://zenodo.org/record/4719436/files/velocity_anndata_mouse_embryonic_stem_cells_DeepCycle_ISMARA.h5ad
```

These anndata objects have been used to reproduce the results in the manuscript [Cell cycle gene regulation dynamics revealed by RNA velocity and deep-learning](https://www.nature.com/articles/s41467-022-30545-8).

## Model Structure
The MutipleCircularRegression model for predicting cell cycle phases from raw gene expression data employs a multi-layered architecture featuring linear transformations in fully connected layers. This design  incorporates three hidden layers, dropout mechanisms for regularization, and output layers predicting sine and cosine components. The model outputs are represented as cartisian values considering the periodicity of the data:
```math
sin_{out} = sin(2*\pi*θ_{out})                  
;
cos_{out} = cos(2*\pi*θ_{out}))
```

## Angle-Based Loss Function
Given the periodic nature of our cell cycle data, we used a custom loss function in our analysis, which measures the difference between predicted and target directions based on their cosine similarity. 

The formula is as follows:
```math
Loss = 1 - cos(θ_{predicted} - θ_{target})
```
where:
- Angle of the predicted direction: $$θ_{predicted} = atan2(x_{cos}, x_{sin})$$ 

- Angle of the target direction: $$θ_{target} = atan2(y_{cos}, y_{sin})$$





```math
P(rt) = $\frac{rt_i}{\sum_{k=1}^N rt_k \}$
```
