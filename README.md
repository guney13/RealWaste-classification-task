# RealWaste-classification-task

Object classification on the RealWaste dataset using a ResNet18 model

RealWaste dataset
- 4,752 images
- 9 classes


Dataset

The dataset is taken from https://archive.ics.uci.edu/dataset/908/realwaste. (The dataset is not loaded to this repository, the existing data folder is for structural purposes only.)

RealWaste dataset contains 9 different imbalanced classes for the classification task. The dataset is splitted into train, validation, and test by maintaining the proportions of the whole dataset. 


Methodolgy

The ResNet18 model is preferred with pretrained weights on the IMAGENET dataset. The last two blocks of the model is then fine-tuned using the obtained train subset from the the existing dataset.


Repo Structure

.
|- data/                # kept for structural purposes but the dataset is not loaded
|- main.ipynb
|- best_res_params.pt   # best performing model parameters
|- README.md            # explanation of the project




