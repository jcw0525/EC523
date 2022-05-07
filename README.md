# EC523
EC523 Project

Update as of 2022.05.06:


Installation and replication instructions:

Download the source code: clone this github repostitory

If you would like, you can download our current and best model (40 epoch, no data augmentation) at https://drive.google.com/file/d/1bfhpANfAnKgsDPsxdA9jOgGCGPPv2g27/view?usp=sharing - this model finished training minutes before the deadline, and although it is not present in the official paper submission, we would still like to show our work (it works very well!)

Download the CVC-ClinicDB dataset: https://www.kaggle.com/datasets/balraj98/cvcclinicdb

For replicating our results, upload CS523_Project.ipynb into Google Colab and the kaggle dataset into your google drive.
Then, run the notebook in colab and grant access to your google drive. You made need to change DATA_DIR = "/content/gdrive/Shared drives/CS523/archive" to whereever you are storing the dataset.


All of the code is in one file 
CS523_Project.ipynb

MODEL: Currently a working implementation of the UNET architecture from (https://arxiv.org/abs/1505.04597):
Ronneberger O., Fischer P., and Brox T. U-Net: Convolutional Networks for Biomedical Image Segmentation. In: Navab N., Hornegger J., Wells W., Frangi A. (eds) Medical Image Computing and Computer-Assisted Intervention–MICCAI 2015. MICCAI 2015. Lecture Notes in Computer Science, vol 9351. Springer, Cham. https://doi.org/10.1007/978-3-319- 24574-4 _28.

DATASET: Using the CVC-ClinicDB dataset of rgb color 612 384x288 colon scans w/ semantic mask labels given for areas of interest

DATALOADER: Our dataloader takes the file path names from the dataset metadata and loads the images into tensors - it also now has infrastructure for data augmentation, specifically rotation shifts and flips. We adapted the Dataloader to our project from https://www.kaggle.com/code/balraj98/polyp-segmentation-in-colonoscopy-frames-deeplab.

VISUALIZER: The visualizer works to help us see the shape of the data - it currently simply displays the colon scans and relevant masks as color images

TRAINING LOOP: The training loop uses Adam with Nesterov Momentum and our implementation of mIOU, or mean intersection over union though a DICE / Jaccard evaluation metric with a Binary Cross Entroy with Logits loss function
