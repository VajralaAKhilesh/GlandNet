
Gland Segmentation - GlaS@MICCAI 2015 Challenge

This project is a solution to the Gland Segmentation (GlaS) Challenge organized at MICCAI 2015. The objective is to develop robust segmentation models to detect glands in H&E stained histological images of colorectal cancer with varying histologic grades.

Description
-----------
Participants are provided with training images and expert-annotated ground truth masks. The challenge involves:
- Building and optimizing segmentation algorithms on the training dataset.
- Validating the models on Test A and Test B datasets.
- Evaluating results using metrics such as Dice Score, F1 Score, and Hausdorff Distance.

Project Structure
-----------------
Grade.csv                - Original spreadsheet from organizers
data.csv                 - Processed CSV for loading data
EDA.ipynb                - Exploratory data analysis
dataloader.ipynb         - Data loading, preprocessing, and augmentation
inference_testA.ipynb    - Inference results on Test A
inference_testB.ipynb    - Inference results on Test B (primary reference)
model.py                 - Experimental model architectures
train.py                 - Training script with W&B logging
metric.py                - Evaluation metric functions
utils.py                 - Helper functions (visualization, preprocessing)
requirements.txt         - Required packages

Setup
-----
1. Clone the repository and navigate to the folder:

   git clone <your-repo-url>
   cd <your-project-folder>

2. Install required dependencies:

   pip install -r requirements.txt
   pip install segmentation-models-pytorch
   pip install --upgrade batchgenerators

Training
--------
To train the model and log results to Weights & Biases (W&B):

   python train.py

Modify train.py as needed to adjust hyperparameters, augmentations, or model choice.

Inference
---------
Use the following notebooks for evaluation and visualization:

- inference_testA.ipynb: Runs inference on Test A dataset
- inference_testB.ipynb: Runs inference on Test B (recommended reference)

Each notebook includes:
- Visualizations of predicted vs ground truth masks
- Overlays and boundary comparisons for metrics like Hausdorff Distance

Results
-------
Metric             | Test A       | Test B       
------------------ | ------------ | -------------
Precision          | 0.93 (±0.06) | 0.90 (±0.08) 
Recall             | 0.93 (±0.06) | 0.90 (±0.08) 
F1 Score           | 0.93 (±0.06) | 0.90 (±0.08) 
Dice Score         | 0.93 (±0.07) | 0.91 (±0.07) 
Hausdorff Distance | 83.35 (±66.77) | 62.36 (±33.02)

Note: All evaluations are based on binary pixel-wise segmentation, not gland-wise object segmentation.

Visualizations
--------------
- Binary segmentation maps of predictions vs ground truth
- Overlay segmentation plots
- Hausdorff Distance boundary comparisons

Future Work
-----------
- Implement gland-wise segmentation
- Extend evaluation to:
  - Object-level Dice Score
  - Object-level F1 Score
  - Object-level Hausdorff Distance

Acknowledgements
----------------
- Dataset and challenge from MICCAI GlaS Challenge 2015
- Evaluation metrics inspired by the work of Hans Pinckaers

License
-------
For research and academic use only. Contact the author for other usage rights.
