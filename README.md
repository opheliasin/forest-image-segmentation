# Image Segmentation for Deforestation Mapping: A Transfer Learning Approach

## Overview
This repository contains the implementation of a deep learning model designed to identify deforestation using image segmentation techniques. Leveraging transfer learning with a modified U-Net architecture and MobileNetV2 as the encoder, our approach aims to provide accurate assessments of deforested areas based on satellite imagery from REDD+ project sites. This work is crucial for enhancing the transparency and accountability of deforestation reporting in environmental conservation efforts.

## Project Description
Deforestation significantly impacts climate change and biodiversity, making effective monitoring essential. This project utilizes a dataset derived from geographical boundaries of REDD+ projects to create images for estimating deforested areas. The modified U-Net model employs skip connections for efficient training and leverages pre-trained weights from MobileNetV2 to enhance feature extraction capabilities.

## Dataset
The dataset consists of satellite images collected via the Sentinel-2 L2A satellite, covering various REDD+ project sites across six countries (Cambodia, Colombia, Democratic Republic of Congo, Peru, Tanzania, and Zambia). The final dataset includes:
- Total Images: 1,518
- Image Patches Used: 893 (after manual curation for cloud coverage and quality)

## Data Preparation Steps
1. Image Collection: Images were gathered using the Sentinel Hub API.
2. Mask Creation: Masks delineating deforested areas were manually created using GIMP.
3. Preprocessing: Images were converted to PNG format, and binary masks were generated for training.

## Model Architecture
The model architecture is based on U-Net, which consists of an encoder-decoder structure:
- Encoder: Utilizes MobileNetV2 for feature extraction.
- Decoder: Upsamples features while preserving spatial information through skip connections.
  
## Key Features
- Transfer Learning: Reduces training time and improves performance on small datasets.
- Modified IoU Metric: Adjusted to handle cases where predicted masks are empty.

## Results
The model's performance was evaluated using metrics such as accuracy, loss, and Intersection over Union (IoU). The results indicate:
- Best Training Accuracy: 0.839 (1-Fold Cross Validation)
- Best Test IoU: 0.443
Visualizations of predictions alongside ground truth masks demonstrate the model's capability to identify deforested areas effectively.

## Future Work
To enhance this project further, we propose:
- Expanding the Dataset: Incorporating more diverse satellite imagery.
- Refining Preprocessing Techniques: Improving cloud detection methods.
- Exploring Alternative Architectures: Investigating other state-of-the-art segmentation models.
- Incorporating Multi-temporal Data: Utilizing time-series data for better context in deforestation analysis.

## Contributors
- Anthony Wu
- Jheel Gala
- Ophelia Sin	
- Venkata Sai Praveen Gunda


