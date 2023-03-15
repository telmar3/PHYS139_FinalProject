# PHYS139_FinalProject
A replication of the DeepClean Algorithm to reduce noise in LIGO gravitational wave signals from: https://journals.aps.org/prresearch/abstract/10.1103/PhysRevResearch.2.033066


## Setup:
Due to specialized packages and libraries, we have provided a requirements.txt file.
In your terminal, run the following command:
`$ pip install -r requirements.txt`

Our dataset, `deepclean-1251335314-4097.h5` is a H5 dataset which contains auxillary channels and their respective data alongside our gravitational wave strain data. This is found in the data folder. 

## API Calls
In order to get the preprocessed data, call the `send_freq_data(), send_time_data(), and the send_post_processing_params()` function in the `data_preprocessing.ipynb` file. 
Place this code at the top of the file you will be importing the data to:
`from ipynb.fs.data_preprocessing import send_data`