## Predicting Cell Cycle Phase from Embryonic Mice Stem Cell Gene Expression Data using Circular Regression with Deep Learning

In the field of biological research, the use of advanced technologies, such as deep learning, has greatly improved our ability to understand complex cellular processes. This study, combining computational biology and cell cycle dynamics, aims to simplify the prediction of cell cycle phases and identify important genes involved. We introduce a new deep learning algorithm, called MultipleCircularRegression, designed specifically for predicting cell cycle phases using raw gene expression data from embryonic mice stem cells. The model effectively captures the cyclical patterns using three connected layers and dropout units for better generalization. Over 800 training cycles, the algorithm consistently reduces cyclic loss, indicating robust learning. Evaluation metrics (MAE = 0.0718, RMSE = 0.1321, R-squared = 0.7779) confirm the model's accuracy in predicting cell cycle phases. By using Captum permutation for feature selection, we identify the top 20 influential genes (e.g., Plk1, Ube2c) and visualize their periodic patterns. This research not only provides a powerful method for predicting cell cycle phases but also highlights the key genes involved in orchestrating these biological processes.

>[!NOTE] 
>This project utilizes mouse embryonic stem cell (mESCs) data obtained from the Zenodo repository. The specific dataset can be retrieved using the following command: 

```bash
curl -LJO https://zenodo.org/record/4719436/files/velocity_anndata_mouse_embryonic_stem_cells_DeepCycle_ISMARA.h5ad
```
