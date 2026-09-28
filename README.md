# RealWaste-classification-task

Object classification on the RealWaste dataset using a ResNet18 model

---

## Dataset

The dataset is taken from [RealWaste Dataset](https://archive.ics.uci.edu/dataset/908/realwaste). 
> **Note:** The dataset is not loaded to this repository, the existing data folder is for structural purposes only.

RealWaste dataset contains 9 different imbalanced classes for the classification task. The dataset is splitted into train, validation, and test by maintaining the proportions of the whole dataset. 


## Methodolgy

The **ResNet18** model is preferred with pretrained weights on the **IMAGENET** dataset. The last two blocks of the model is then fine-tuned using the obtained train subset from the the existing dataset.


Repo Structure

'''
.
|- data/                # kept for structural purposes but the dataset is not loaded
|- main.ipynb
|- best_res_params.pt   # best performing model parameters
|- README.md            # explanation of the project
'''




## How to Reproduce

### 1. Clone the repository

```bash
git clone https://github.com/guney13/RealWaste-classification-task.git
cd RealWaste-classification-task
```

### 2. Set up the environment

With **Python 3.14**

```bash
python3 -m venv venv
source venv/bin/activate        # for Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Download the dataset

Download RealWaste from the [RealWaste Dataset](https://archive.ics.uci.edu/dataset/908/realwaste), extract it, and place the `RealWaste` folder under `data/`. The data/ folder should look like this:

```
data/
└── RealWaste/
    ├── Cardboard/
    ├── Food Organics/
    ├── Glass/
    ├── Metal/
    ├── Miscellaneous Trash/
    ├── Paper/
    ├── Plastic/
    ├── Textile Trash/
    └── Vegetation/
```

> **Note:** The notebook reads images from `data/RealWaste` (`DATA_DIR`), so the folder name and location must match exactly.

### 4. Run the notebook

```bash
jupyter notebook main.ipynb
```

Run all cells from top to bottom. The program will automatically choose **CUDA**, **Apple MPS**, or the **CPU**, depending on what is available.
> **Note:** To evaluate the provided `best_res_params.pt` without retraining, skip the training cell and run the cells after it. Running the training cell **overwrites** the saved `best_res_params.pt`.

