# PHYS139_FinalProject
A replication of the DeepClean Algorithm to reduce noise in LIGO gravitational wave signals from: https://journals.aps.org/prresearch/abstract/10.1103/PhysRevResearch.2.033066


## Setup:
Due to specialized packages and libraries, we have provided a requirements.txt file.
In your terminal, run the following command:
`$ pip install -r requirements.txt`

Our dataset, `deepclean-1251335314-4097.h5` is a H5 dataset which contains auxillary channels and their respective data alongside our gravitational wave strain data. This is found in the data folder or by followiung the dropbox link. 


## Files:
### data_preprocessing.ipynb
This notebook is the preprocessing file which takes in the raw GW strain and Witnes noise data and applied our preprocessing pipeline to it. 
The pipeline has the following structure:
 - Batching
 - Test Train split
 - Butterworth filter creation and application
 - Z-score normalization
 - Windowing
 - Welch method for custom loss function
 
### cnn_model.ipynb
This is the actual model architecture. This notebook is where the model is trained and tested. 

### data_postprocessing.ipynb
This notebook reverses some of the preprocessing in order to return the predicted data to the original units, and range. The postprocessing includes:
 - Butterworth filtering
 - Inverse Z-score
 
Furthermore, the SNR and noise reduction pipeline is integrated into this notebook. The noise reduction and SNR are done using the predicted noise data given a GW strain input into the model after postprocessing
