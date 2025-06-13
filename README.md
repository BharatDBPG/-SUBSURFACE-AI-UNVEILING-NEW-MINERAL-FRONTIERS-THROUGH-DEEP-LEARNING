# **SUBSURFACE AI: Unveiling New Mineral Frontiers through Deep Learning**

This repository was created as part of the **IndiaAI Hackathon on Mineral Targeting 2025**, in collaboration with the **Geological Survey of India (GSI)**. The goal is to identify concealed and deep-seated mineralized zones across a 39,000 sq. km area in Karnataka and Andhra Pradesh using deep learning techniques applied to integrated geoscientific data.


## **1. Data Sources**

The datasets used in this project were compiled from multiple geoscientific domains:

* **Geological Maps** (1:25,000 and 1:50,000 scale): Faults, folds, dykes, lithology, lineaments
* **Geochemical Data**: Elemental concentrations of REE, Ni-PGE, Cu, Au, etc.
* **Geophysical Data**: Elevation, gravity, Bouguer anomalies, density, magnetic susceptibility
* **Mineral Occurrence Records**: Historical data used for label assignment
* All datasets were reprojected to EPSG:32643 and standardized on **4 km × 4 km grid** cells.


## **2. Project Approach (Summary)**

* Created uniform spatial grids for the region and overlaid geoscientific datasets.
* Assigned binary labels to each grid cell: `1` for mineralized, `0` for non-mineralized.
* Handled missing values, concatenated structural data from different scales, and reshaped data for model input.
* Trained and validated a deep learning model using this gridded, structured dataset.



## **3. Algorithm Used**

* **Optimized Long Short-Term Memory (LSTM)** Neural Network

  * Architecture: LSTM → Dropout → Dense (ReLU) → Dropout → Dense (Sigmoid)
  * Loss: Binary Crossentropy | Optimizer: Adam
  * Accuracy: **91%** on test data
  * Evaluation: Confusion Matrix, Classification Report (Precision, Recall, F1-Score)


## **4. Outputs and Visualizations**

* **Predicted Mineral Zones** across 3 different grid resolutions:

  * 5 km Grid → 1 zone
  * **4 km Grid → 3 zones (Optimal)**
  * 3 km Grid → 1 zone
* Visualized predicted mineral zones on geospatial maps
* Sample output chart:

  
  ![Predicted Map](predicted_map.png)

  



## **5. Conclusion**

This project successfully demonstrates the power of deep learning, particularly LSTM, in **data-driven mineral prospectivity mapping**. The **4 km × 4 km grid resolution** offered the best balance between spatial accuracy and model performance.
Three promising mineral zones were predicted and finalized for **further geological validation**, laying the foundation for advanced AI-assisted mineral exploration in India.

Here’s a polished and professional version of your README section that clearly explains the contents and structure of your repository:

---

###  Repository Structure and Access

This repository contains all the necessary components used in our mineral prospectivity mapping project. Below is a description of each folder and its contents:

* **`dataset_file/`**: Contains the links to the original raw geoscientific datasets used in this study. These files can be downloaded for reference or further use.

* **`preprocessed_data/`**: Includes the processed and cleaned dataset, ready for input into the machine learning models. This data was derived from raw sources through spatial integration and standardization.

* **`preprocessed_data_code/`**: Contains the complete preprocessing scripts used to transform and prepare the raw geospatial data, including spatial overlays, labeling, handling missing values, and grid generation.

* **`mineral_prediction_using_grid_approach/`**: Includes model training scripts using XGBoost and LSTM on the gridded dataset, along with code for predicting new mineralized regions.

* **`spatial_distance_analysis_of_predicted_minerals/`**: Provides the scripts used for calculating spatial distances between newly predicted mineral zones at different grid resolutions (3 km, 4 km, and 5 km).

* **`predicted_map/`**: Contains visual outputs (e.g., map images) of the newly predicted mineral-rich zones for easier interpretation and presentation.



