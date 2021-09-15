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
* [Webscraping Files](/Webscraping)

## Overview
In this project I sought to build an image classifier similar to the ones on social media platforms, capable of filtering out sexually explicit content. After further research I learned that image filters and content filtering generally speaking were very sensitive topics; many social platforms have received lash back from users for their non-inclusive content filtering. With this knowledge the project grew to include 4 different final CNN network models.

> 1) 3-class convolutional neural network with `neutral`, `sexy`, `explicit` image classes
> 2) 5-class convolutional neural network with `neutral`, `sexy`, `explicit`, `violent`, `breastfeeding` image classes
> 3) Binary convolutional neural network with `SFW` (Suitable For Work) and `NSFW` (Not Suitable For Work) image classes using only photos from the first three classes: `neutral`, `sexy`, `explicit`
> 4) Binary convolutional neural network with `SFW` and `NSFW` image classes using all photos from the 5 classes: `neutral`, `sexy`, `explicit`, `violent`, `breastfeeding`

The `violent` category was included to account for different types of explicit, NSFW images, and the `breastfeeding` class was added in response to protest following the #freethenipple movement and Instagram's banning of breastfeeding photos (which has since been unbanned) several years ago.

## Business Understanding
Social media spans all corners of the world - Facebook last recorded [2.89 billion active users](https://www.statista.com/statistics/264810/number-of-monthly-active-facebook-users-worldwide/) in the second quarter of 2021 and Intagram and Reddit fall behind with [1.074 billion](https://www.omnicoreagency.com/instagram-statistics/) and [54 million](https://www.oberlo.com/blog/reddit-statistics) active users. With a platform reaching so many people, content filtering is crucial to protect users from inappropriate and possibly traumatizing images. Facebook even has an entire team of [content moderators](https://www.theverge.com/2019/2/25/18229714/cognizant-facebook-content-moderator-interviews-trauma-working-conditions-arizona) whose entire days are spent manually reviewing photos and posts for this very reason.

Despite the good intent behind content filtering on social platforms, Instagram and Facebook have received a lot of public scrutiny regarding the #freethenipple movement, claims racial bias when banning accounts and images, and even lawsuits against the platforms for violation of user freedom of speech/expression. Machine learning models. My goal was to build a image classifier capable of filtering explicit sexual content while also remaining inclusive of all types of people and of their content. I created numerous binary and multiclass image classifiers to protect user freedom as well as protect their "innocence."

## Data Understanding and Preparation
I collected my `neutral`, `sexy`, `explicit` image classes through the [NSFW Data Scraper](https://github.com/alex000kim/nsfw_data_scraper) on Github. The data was noisy, misclassifying many `sexy` and `explicit` images with one another which would be detrimental to the integrity of my classifier; I manually sorted through the images to ensure that my model performance and accuracy was not negatively impacted by the misclassifications. After re-classifying and removing corrupt images, I ended with total of 92,443 photos to feed my classifier. Note that although I did sort through these images myself, there was plenty of room for human error due to the sheer number of images and even after filtering, I still came across several misclassified images, specifically within the `sexy` category.

Images were split into Train/Test/Split folders using the `os` and `shutil` libraries. Images were then converted to grayscale to 1) Reduce computational complexity and 2) Prevent possible racial bias in the event that racial minorities were under or over represented within certain image classes. Image quality reduced to (80 x 80), as after some research I learned this was a standard image size for CNN models. 

Images were webscraped from Google Images to provide the `violent` and `breastfeeding` categories and the .py files for scraping can be found in the [webscraping](/Webscraping) folder for future use. Even with a Google search, these images were still hard to come by and only contain between 300-400 photos within each category. The `violent` photos were especially hard to come by. In the future I would need to find more of these photos possibly from social media sites themselves and I would need to scrape from Google webpages. The very large class imbalance was expected to play a large role in the performance of my models, even with data augmentation.

## Analysis



## Predictive Models
I began creating CNN models for only
    
    
## Conclusions
As predicted, my model had the most difficulty distinguishing between `sexy` and `explicit` photos with a greater tendancy to mistake sexy photos for explicit ones. 

## Contributors
- Samantha Baltodano <br>
    Github: [sbaltodano](https://github.com/sbaltodano)<br>
