---
title: IE 561 Super Resolution project 
description: Using super resolution algorithms to refine the arctic satellite imageries
--- 

# What are the challenges we face currently with the arctic satellite imageries? 


Why is it important?

What are the current approaches?

What is it about the current approaches that aren't good enough?\

What is our new approach?



For recent few decades, the arctic regions have gone through major rapid climate changes, directly affecting the geology of the environment. There are damages done to the communities on the coastline and permafrost terrains as the terrains erode. The PIPER project (People Infrastructure Permafrost Resilience) addresses this problem by understand the relationship and mutual impacts of continued climate change in the arctic reflected in the following components: permafrost degradation and coastal erosion, civil infrastructure and development, and community well-being and sociodemographic and cultural resilience.

Currently, the required high-resolution imageries are only available in high temporal resolutions (low frequency of imageries throughout the year). In order to make up for this shortcoming, imageries with high temporal resolutions are adopted for the studies. However, the high temporal resolution imageries are often low in spatial (visual) resolution, limiting the clear understanding of the coastline erosions. 

This team's project was focused on helping the project gain better insight of the coastal erosion through improving the resolution of the satellite imageries. By having access to higher resolution imageries of the target regions, significant connections can be deduced between the possible causes and the erosion status. The super resolution algorithms implemented for this project were SRCNN (Super Resolution Convoluted Neural Network) and SRResnet (Super Resolution Residual Network). Two models were ran in comparison using the same images of test set, yielding PSNR (Peak Signal-to-Noise Ratio) scores.



# Introduction on Super Resolution technology

![](http://www.sysu-hcp.net/wp-content/uploads/2017/06/4.png)
_Visual Comparisons of SR image outputs (PSNR/SSIM)_ [1]


Super resolution is a class of technique that enhences the resolution of low resolution (LR) images into high resolution (HR) images. Many different algorithms have been developed and implemented to execute this task. Some of the popular names include SRCNN, F-SRCNN (Fast SRCNN), VDSR (Very Deep Super Resolution), SRF (Super Resolution Forests), Structure-Preserving Image Super Resolution (SPSR) and SRRResNet. In order to quantifiably measure the performance of the algorithms and compare them to one another, there are metrics such as PSNR and SSIM (Structural Similarity).


# Methods
The project underwent the following steps.
1. Compare the models that are currently being used; SRCNN and SRResnet
2. Compare the two models by PSNR score, pick the best model to use for Dr Farquharson.
3. Create the pipeline for Dr Farquharson. (Ideally simple enough that she only has to type in image size and file location.)
4. Designing and submitting Github project presentation page
### SRCNN
### SRResNet



# Model Performances

Performance comparisons

Performance analysis

# Conclusion

Limitations and difficulties


# Future Works


