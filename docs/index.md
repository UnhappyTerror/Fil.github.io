---
title: IE 561 Super Resolution project 
description: Using super resolution algorithms to refine the arctic satellite imageries
--- 

# What are the challenges we face today with the available arctic satellite imageries?



![](https://seagrant.uaf.edu/topics/environmental-hazards-alaskas-coasts/flooding-erosion/images/mvc-009f.jpg)
<br />
_Damage due to coastal erosion in Sheshmaref, Alaska_ [1]

### Why is this important?

For recent few decades, the arctic regions have gone through major rapid climate changes, directly affecting the geology of the environment. There are damages done to the communities on the coastline and permafrost terrains as the terrains erode. The PIPER project (People Infrastructure Permafrost Resilience) addresses this problem by understand the relationship and mutual impacts of continued climate change in the arctic reflected in the following components: permafrost degradation and coastal erosion, civil infrastructure and development, and community well-being and sociodemographic and cultural resilience.

![](https://prd-wret.s3.us-west-2.amazonaws.com/assets/palladium/production/s3fs-public/styles/full_width/public/thumbnails/image/GibbsRichmond2015_NorthSlopeShorelineChangeSM.jpg)
_Alaskan shoreline erosion rate_ [2]

### What are the current approaches and what are their shortcomings?

Currently, the required high-resolution imageries are only available in high temporal resolutions (low frequency of imageries throughout the year). In order to make up for this shortcoming, imageries with high temporal resolutions are adopted for the studies. However, the high temporal resolution imageries are often low in spatial (visual) resolution, limiting the clear understanding of the coastline erosions. 

### What is our new approach?

This team's project was focused on helping the project gain better insight of the coastal erosion through improving the resolution of the satellite imageries. By having access to higher resolution imageries of the target regions, significant connections can be deduced between the possible causes and the erosion status. The super resolution algorithms implemented for this project were SRCNN (Super Resolution Convoluted Neural Network) and SRResnet (Super Resolution Residual Network). Two models were ran in comparison using the same images of test set, yielding PSNR (Peak Signal-to-Noise Ratio) scores for comparison.



# Introduction on Super Resolution technology

![](https://www.researchgate.net/profile/Chen-Change-Loy/publication/305779418/figure/fig3/AS:390953274757123@1470221932952/The-butterfly-image-from-the-Set5-dataset-with-an-upscaling-factor-3.png)
<br />
_Visual Comparisons of SR image outputs_ [3]


Similar to the deep learning and computer vision technologies, super resolution started getting more attention in academia and industries as the data availability and computational capability increased drastically in the past decade. Super resolutio
n is a class of technique that enhences the resolution of low resolution (LR) images into high resolution (HR) images. Many different algorithms have been developed and implemented to execute this task. Some of the popular names include SRCNN, F-SRCNN (Fast SRCNN), VDSR (Very Deep Super Resolution), SRF (Super Resolution Forests), SPSR (Structure-Preserving Image Super Resolution), and SRRResNet. In order to quantifiably measure the performance of the algorithms and compare them to one another, there are metrics such as PSNR and SSIM (Structural Similarity).


# Methods

### Steps

#### 1) Splitting the image

![](http://www.andrewjanowczyk.com/wp-content/uploads/2016/07/small_tiles.png)
<br />
_Example of splitting large image into small pieces_ [4]

The Team selected greyscale satellite imagery taken from Kaktovik, Alaska that was taken in the 1960’s as the training and test set. This image was sliced into smaller images each in the size of 128 x 128 pixels in order to procure ample training and test set data objectives for the algorithm. The super resolution models were pre-trained algorithms from the recognized sources.

#### 2) Run data objects through algorithm for refinement

The same image set was used for both super resolution algorithms for apples-to-apples performance comparison. For this team's case, refinement of each 128x128 image slice took around 0.15 seconds to process, which summed up to around 12 minutes to process 6,000 images in total.

#### 3) Combining the split images back together

After the split imageries go through super resolution, the images are combined back into its original shape and order for intuitive visual comparison with the original image and the competing algorithm's output.

#### 4) Visual comparison and PSNR comparison

Side by side comparison of the input and the output images not only provide direct and intuitive comparison between the before and after, but also provides insights on how the images were affected by the algorithm. Certain types of patterns and/or changes were spotted through this process.



### SRCNN (Super Resolution Convoluted Neural Network)

SRCNN model code

```Python
def model():
    
    SRCNN = Sequential()
    
    SRCNN.add(Conv2D(filters=128, kernel_size = (9, 9), kernel_initializer='glorot_uniform',
                     activation='relu', padding='valid', use_bias=True, input_shape=(None, None, 1)))
    SRCNN.add(Conv2D(filters=64, kernel_size = (3, 3), kernel_initializer='glorot_uniform',
                     activation='relu', padding='same', use_bias=True))
    SRCNN.add(Conv2D(filters=1, kernel_size = (5, 5), kernel_initializer='glorot_uniform',
                     activation='linear', padding='valid', use_bias=True))

    adam = Adam(lr=0.0003)
    
    SRCNN.compile(optimizer=adam, loss='mean_squared_error', metrics=['mean_squared_error'])
    
    return SRCNN
```

PSNR result

![fig1](https://user-images.githubusercontent.com/74638365/116183696-5d230180-a6ec-11eb-85f7-a9ca1f68d07e.jpg)
<br />
![fig2](https://user-images.githubusercontent.com/74638365/116183700-5f855b80-a6ec-11eb-8232-948ed7851bfb.jpg)
_Original input vs SRCNN output_


### SRResNet (Super Resolution Residual Network)

Code source

```Python
print("Hello, World!")
```

PSNR result

![WeChat Image_20210427001532 - Copy](https://user-images.githubusercontent.com/74638365/116193281-1e497780-a6fd-11eb-94fe-1340caed6225.jpg)
![WeChat Image_20210427001532](https://user-images.githubusercontent.com/74638365/116193297-22759500-a6fd-11eb-8aa3-40c1b8d56dd8.jpg)

![WeChat Image_20210427001524 - Copy](https://user-images.githubusercontent.com/74638365/116193337-315c4780-a6fd-11eb-83da-c290bfca3646.jpg)
![WeChat Image_20210427001524](https://user-images.githubusercontent.com/74638365/116193334-30c3b100-a6fd-11eb-930c-ec6dfd661517.jpg)



# Conclusion

### Final recommendation on the algorithm choice

Both algorithms showed significant results in improving the resolution and definition of the satellite images. Comparing the two techniques, SRCNN yielded higher PSNR score, proving itself to be favorable. 

### Limitations and difficulties during the project



# Future Works

The team focused on building and testing the model with one specific satellite imagery. While this was suffice for the first step, in order to build a stronger case on its performance and further develop its uses, feeding additional, relevant sets of satellite images is expected to be beneficial.

Moreover, as mentioned above, there are numerous pre-established super resolution algorithms available for usage. While this team only got to explore a few of the options due to limitations in time and proficiencies in the domain, exploring more algorithms to weigh the options and to find the most suitable tool for the arctic environment satellite imageries will be helpful in moving forward with PIPER project.



# References
[1] https://seagrant.uaf.edu/topics/environmental-hazards-alaskas-coasts/flooding-erosion/

[2] https://www.usgs.gov/center-news/updated-assessment-erosion-rates-alaska-s-arctic-coast?qt-news_science_products=3#qt-news_science_products

[3] https://www.researchgate.net/figure/The-butterfly-image-from-the-Set5-dataset-with-an-upscaling-factor-3_fig3_305779418

[4] http://www.andrewjanowczyk.com/dividing-and-re-merging-large-images-humpty-dumpty/
