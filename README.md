# CSGNN
The code for paper "CSGNN: Contrastive Self-Supervised Graph Neural Network for MolecularInteraction Prediction"

## 1 Overview
The repository is organized as follows:

+ `data/` contains the datasets used in the paper;
+ `parms_setting.py` contains all hyperparameters adopted by CSGNN;
+ `data_preprocess.py` contains the preprocess of data before training;
+ `layer.py` contains mix-hop GNN layers and contrastive learning GNN layers;
+ `instantiation/` contains the code which instantiate the CSGNN;
+ `train.py` contains the training and testing code on datasets;
+ `utils.py` contains preprocessing functions of the data (e.g normalize...);
+ `main.py` contains entry to CSGNN (e.g normalize...);


## 2 Dependencies
* numpy == 1.18.5
* scipy == 1.5.2
* sklearn == 0.23.2
* torch == 1.5.0
* torch-geometric == 1.6.1
* networkx == 2.4


### 3 Example
Here we provide several example of using CSGNN
To run CSGNN with GCN aggregator on DTI network using "uniform" as initial features and ouput the result to test.txt, execute the following command:

	python main.py --aggregator GCN --feature_type uniform --in_file data/DTI.edgelist --out_file test.txt
	
To run CSGNN with GCN aggregator on DDI network using one-hot coding as initial features and ouput the result to test.txt, execute the following command:
	
	python main.py --aggregator GIN --feature_type one_hot --in_file data/DDI.edgelist --out_file test.txt