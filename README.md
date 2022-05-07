# EC523
EC523 Project

Update as of 2022.05.06:


Installation and replication instructions:

Download the source code: clone this github repostitory
Download teh CVC-ClinicDB dataset: https://www.kaggle.com/datasets/balraj98/cvcclinicdb

For replicating our results, upload CS523_Project.ipynb into Google Colab and the dataset into your google drive.
Then, simply run the notebook in colab and grant access to your google drive. You made need to change DATA_DIR = "/content/gdrive/Shared drives/CS523/archive" to whereever you are storing the dataset.


All of the code is in one file 
CS523_Project.ipynb

MODEL: Currently a working implementation of UNET architecture

DATASET: Using the CVC-ClinicDB dataset of rgb color 384x288 colon scans w/ semantic mask labels given for areas of interest

DATALOADER: Our dataloader takes the file path names from the dataset metadata and loads the images into tensors - it also has infrastructure for data augmentation, such as rotation shifts and flips

VISUALIZER: The visualizer works to help us see the shape of the data - it currently simply displays the colon scans and relevant masks as color images

TRAINING LOOP: The training loop uses Adam with Nesterov Momentum and our implementation of mIOU, or mean intersection over union though a DICE loss function
