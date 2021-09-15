# Social Media Content Filtering
Samantha Baltodano

![alt text](Visuals/file-20210604-23-e0is4c.jpeg)


## Table of Contents
* [Overview](#overview)
* [Business Understanding](#business-understanding)
* [Data Understanding and Preparation](#data-understanding-and-preparation)
* [Analysis](#analysis)
* [Predictive Models](#predictive-models)
* [Conclusions](#conclusions)
* [Contributors](#contributors)


## Repository Links
* [Images](/Visuals)
* [Data](https://github.com/alex000kim/nsfw_data_scraper)

## Overview

Notes - 
Stakeholder -> fb or instagram 
Facebook last recorded [2.89 billion active users](https://www.statista.com/statistics/264810/number-of-monthly-active-facebook-users-worldwide/) in the secnd quarter of 2021
Intagram and Reddit fall behind with [1.074 billion](https://www.omnicoreagency.com/instagram-statistics/) and [54 million](https://www.oberlo.com/blog/reddit-statistics) active users

## Business Understanding
Instagram and facebook have received a lot of public scrutiny regarding the #freethenipple movement and possible racial bias when banning accounts and images.

## Data Understanding and Preparation
I collected my `neutral`, `sexy`, `explicit` image classes through the [NSFW Data Scraper](https://github.com/alex000kim/nsfw_data_scraper) on Github. The data was noisy, misclassifying many `sexy` and `explicit` images with one another which would be detrimental to the integrity of my classifier; I manually sorted through the images to ensure that my model performance and accuracy was not negatively impacted by the misclassifications. After classifying and removing corrupt images, I ended with total of 92,443 photos to feed my classifier. 

Split images into Train/Test/Split folders using the `os` and `shutil` libraries

<INSERT IMAGE/ Maybe >

Images were converted to grayscale to 1) Reduce computational complexity and 2) Prevent possible racial bias in the event that racial minorities were under or over represented within certain image classes. Image quality reduced to (256 x 256), as after some research I learned this was a standard image size for CNN models.
    
<INSERT IMAGE/ Maybe >

It was important that I test the accuracy of my model on breastfeeding photos which were not available in the NSFW Data Scraper. In this case, I webscraped <INSERT NUMBER/ > breastfeeding photos from Google Images and again filtered through the images manually to remove noise. After a best performing model was determined based on it's performance on the NSFW Data Scraper images, I trained it the same model on the breast feeding photos and it returned an accuracy of <xx%> on unseen breastfeeding photos.

## Analysis



## Predictive Models
*** EXPLAIN FINAL MODEL LAYERS AND THEIR PURPOSE/EFFECT
    
<INSERT FINAL MODEL SUMMARY/ >
    
<INSERT FINAL MODEL ACCURACY AND RECALL/CONFUSION MATRIX>
    
    
## Conclusions
As predicted, my model had the most difficulty distinguishing between `sexy` and `explicit` photos with a greater tendancy to mistake sexy photos for explicit ones. 

## Contributors
- Samantha Baltodano <br>
    Github: [sbaltodano](https://github.com/sbaltodano)<br>
