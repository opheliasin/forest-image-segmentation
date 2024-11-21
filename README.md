# Forest Image Segmentation
- Anthony Wu, awu3	
- Jheel Gala, jgala	
- Ophelia Sin, oysin	
- Venkata Sai Praveen Gunda, vgunda

## Methodology

### Dataset
The dataset used in this project is generated based on the dataset compiled by [West et al. 2023](https://www.science.org/doi/10.1126/science.ade3535), containing geographical boundaries of Verified Carbon Standard (VCS) -certified [REDD+](https://unfccc.int/topics/land-use/workstreams/redd/what-is-redd#:~:text='REDD'%20stands%20for%20'Reducing,enhancement%20of%20forest%20carbon%20stocks.) projects investigated. The original dataset included shapefiles of the 27 sites from 6 countries (Cambodia, Colombia, Democratic Republic of Congo, Peru, Tanzania, and Zambia).

Previously, we've downloaded 1518 Sentinel-2 L2A images (10-m resolution) of these sites with [SentinelHub API](https://www.sentinel-hub.com/), collected during the summer months (June, July and August) between the years 2016 to 2018. The downloaded images were cropped to match the geographic boundaries of the sites. Then, we randomly extracted ten 224 x 224 image patches from each image. These image patches were in TIFF format and contain the 3 visible channels (red, green, and blue). 

The image patches were reviewed manually - kept or discarded based on cloud coverage or existence of pixels with null values - and classified as forested or deforested. For our initial dataset, we retained 893 image patches. 

To reduce the time spent on preparing the final dataset for this specific project, we randomly selected 121 224x224 images. The following table shows the number of images selected per project

| Project | Total Images | Deforested Images |Forest Images| 
|:---------------|-------------:|-------------:|-----------------:|
| Colombia_1566  |           36 |           26 |               10 |
| DRC_934        |            2 |            2 |                0 |
| Peru_1067      |           39 |           39 |                0 |
| Peru_1360      |            2 |            2 |                0 |
| Peru_2278      |            1 |            1 |                0 |
| Peru_844       |           16 |            1 |               15 |
| Peru_944       |            4 |            4 |                0 |
| Peru_958       |            1 |            1 |                0 |
| Peru_985       |            2 |            2 |                0 |
| Tanzania_1325  |            3 |            3 |                0 |
| Zambia_1202    |            4 |            4 |                0 |
| Zambia_1775    |           11 |           11 |                0 |

### Masking
- For each image in our dataset, we created a mask to mark deforested areas using [GIMP](https://www.gimp.org/), an open-sourced image editor. Deforested areas are colored with black paint, whereas forested area remained transparent. 

## Limitations
We acknowledge multiple limitations in our project:
1. The masks we've drawn are not completely accurate. 
