---
title: IE 561 Super Resolution project 
description: Using super resolution algorithms to refine the arctic satellite imageries
--- 

# What are the challenges we face currently with the arctic satellite imageries???? 



![](https://seagrant.uaf.edu/topics/environmental-hazards-alaskas-coasts/flooding-erosion/images/mvc-009f.jpg)
<br />
_Erosion in Sheshmaref, Alaska_ [1]

### Why is it important?

For recent few decades, the arctic regions have gone through major rapid climate changes, directly affecting the geology of the environment. There are damages done to the communities on the coastline and permafrost terrains as the terrains erode. The PIPER project (People Infrastructure Permafrost Resilience) addresses this problem by understand the relationship and mutual impacts of continued climate change in the arctic reflected in the following components: permafrost degradation and coastal erosion, civil infrastructure and development, and community well-being and sociodemographic and cultural resilience.

![](https://prd-wret.s3.us-west-2.amazonaws.com/assets/palladium/production/s3fs-public/styles/full_width/public/thumbnails/image/GibbsRichmond2015_NorthSlopeShorelineChangeSM.jpg)
_Alaskan shoreline erosion rate_ [2]

### What are the current approaches and what are its shortcomings?

Currently, the required high-resolution imageries are only available in high temporal resolutions (low frequency of imageries throughout the year). In order to make up for this shortcoming, imageries with high temporal resolutions are adopted for the studies. However, the high temporal resolution imageries are often low in spatial (visual) resolution, limiting the clear understanding of the coastline erosions. 

### What is our new approach?

This team's project was focused on helping the project gain better insight of the coastal erosion through improving the resolution of the satellite imageries. By having access to higher resolution imageries of the target regions, significant connections can be deduced between the possible causes and the erosion status. The super resolution algorithms implemented for this project were SRCNN (Super Resolution Convoluted Neural Network) and SRResnet (Super Resolution Residual Network). Two models were ran in comparison using the same images of test set, yielding PSNR (Peak Signal-to-Noise Ratio) scores for comparison.



# Introduction on Super Resolution technology

![](https://www.researchgate.net/profile/Chen-Change-Loy/publication/305779418/figure/fig3/AS:390953274757123@1470221932952/The-butterfly-image-from-the-Set5-dataset-with-an-upscaling-factor-3.png)
<br />
_Visual Comparisons of SR image outputs_ [3]


Super resolution is a class of technique that enhences the resolution of low resolution (LR) images into high resolution (HR) images. Many different algorithms have been developed and implemented to execute this task. Some of the popular names include SRCNN, F-SRCNN (Fast SRCNN), VDSR (Very Deep Super Resolution), SRF (Super Resolution Forests), SPSR (Structure-Preserving Image Super Resolution), and SRRResNet. In order to quantifiably measure the performance of the algorithms and compare them to one another, there are metrics such as PSNR and SSIM (Structural Similarity).


# Methods

### Steps

#### 1) Splitting the image

The Team selected greyscale satellite imagery taken from Kaktovik, Alaska that was taken in the 1960’s as the training and test set. This image was sliced into smaller images each in the size of 128 x 128 pixels in order to procure ample training and test set data objectives for the algorithm. The super resolution models were pre-trained algorithms from the recognized sources.

#### 2) Run data objects through algorithm for refinement

asdf

#### 3) Combining the split images back together

After the split imageries go through super resolution, the images are combined back into its original shape and order for intuitive visual comparison with the original image and the competing algorithm's output.

#### 4) Visual comparison and PSNR comparison

asdf

### SRCNN (Super Resolution Convoluted Neural Network)

Code source

```Python
print("Hello, World!")
```

Application steps

PSNR result

### SRResNet (Super Resolution Residual Network)

Code source

```Python
print("Hello, World!")
```

Application steps

PSNR result


# Model Performances

Performance comparisons

Performance analysis


# Conclusion

Final recommendation on the algorithm choice

Limitations and difficulties during the project


# Future Works

Try additional, relevant training sets on the algorithm

Utilize other super resolution algorithms



# References
[1] https://seagrant.uaf.edu/topics/environmental-hazards-alaskas-coasts/flooding-erosion/

[2] https://www.usgs.gov/center-news/updated-assessment-erosion-rates-alaska-s-arctic-coast?qt-news_science_products=3#qt-news_science_products

[3] https://www.researchgate.net/figure/The-butterfly-image-from-the-Set5-dataset-with-an-upscaling-factor-3_fig3_305779418
