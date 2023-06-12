# InSAR-based-pixel-selection
The program MTInSAR_convlstm_pixel_selection can be used for selecting PS pixels in multi-temporal InSAR processing. 

Input: A stack of interferograms in .mat format (exported from WabInSAR software developed by Manoochehr Shirzaei). WabInSAR software is open access and can be downloaded from the following link:¶ https://sites.google.com/vt.edu/eadar-lab/software

Output: A map with labels 0 and 1, 0 denoting non-PS pixels, and 1 denoting PS pixels

The interferograms are divided into image patches of 100 by 100 pixels and then fed to the network for training. Further, the time series is sampled to a range of 20-30 time steps for better learning. 

## Instructions for running the program:

1. Use requirements.txt to install necessary libraries for the program. Follow these steps:

  	In your shell (or command prompt)

	(i) Go to the directory where requirements.txt is located
	(ii) activate your virtualenv (if you create a separate virtual envcironment for this program)
	(iii) run pip install -r requirements.txt 

2. The input data for this program can be downloaded from the following link:
https://doi.org/10.7294/23478236

3. The example dataset has two files: (i)interferogram stack and (ii) labels (measurement pixel or not). The file ph_im.mat contains time series of interforgrams generated from WabInSAR software v5.3. The dimension is w*h*n, where w=width, h=height and n=number of SAR interferograms. The file elpx.mat contains pixel locations in image (elpx_imloc) and row (elpx_loc) forms for the selected measurement points after the pixel selection step.


## Please cite the following if using the program and data:

Tiwari, Ashutosh; Shirzaei, Manoochehr (2023). Deep learning for efficient selection of measurement pixels in multi-temporal InSAR processing. University Libraries, Virginia Tech. Dataset. https://doi.org/10.7294/23478236 


## Acknowledgements:

Manoochehr Shirzaei: Conceptualization, input data preparation, validation and funding.
Avadh Bihari Narayan: Data preparation, testing and validation for earlier versions of convolutional LSTM model.
Onkar Dikshit: Funding support for earlier version
