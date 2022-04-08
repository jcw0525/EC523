# EC523
EC523 Project

Update as of 2022.04.07:

MODEL: Currently a working implementation of UNET architecture; still need to validate results against UNET paper

DATASET: Using the CVC-ClinicDB dataset of rgb color 384x288 colon scans w/ semantic mask labels given for areas of interest

DATALOADER: Our dataloader takes the file path names from the dataset metadata and loads the images into tensors

VISUALIZER: The visualizer works to help us see the shape of the data - it currently simply displays the colon scans and relevant masks as color images

TRAINING LOOP: The training loop uses stochastic gradient descent and our implementation of mIOU, or mean intersection over union as a loss function
