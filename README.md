# Self-Driving-Cars-Project
*Building a DL CV Model for Image Detection With Semantic Segmentation*

**Overview:**

For the final group project of the ITC Data Science bootcamp, our team decided to try and investigate deep learning models for image segmentation and lane detection, which are building blocks for self driving cars 🚘. The ability to detect various images that a car may encounter, as well as the ability to detect lanes, are fundamental to the progress of atonomous vehicles, for obvious reasons. 

We chose this topic because the field interests us and we knew that it would be challenging on a technical level. Of course it is difficult to achieve results that are good enough for a self driving car with a small team and only a few weeks, but we were able to train a model with over 98% accuracy and high values of other metrics. 

**Dataset:**

The dataset we used for training and testing can be found here: https://www.kaggle.com/kumaresanmanickavelu/lyft-udacity-challenge, and was generated for the Lyft Udacity challenge from videos of the CARLA driving simulator. The dataset contains 5 sets of 1000 images and labels. In order to improve the performance of the models, we augmented the data by tilting the images in various ways, thereby increasing the number of images to 25,000. 

Although we were unsuccessful due to techinical difficulties, we had planned to use the BDD100K dataset (https://doc.bdd100k.com/download.html) to grealy increase our training and testing data. Using this dataset, and potentially increase it's utility by using augmentation, is one of the open ended questions of this project.

**Models:**

We first started by building a basic UNET model, for both image segmentation and lane detection. The implementation of the U-Net that was used as the baseline models was taken from a Kaggle Notebook written by Oluwatobi Ojekanmi and Seidu Idris, which can be found here: https://www.kaggle.com/oluwatobiojekanmi/carla-image-semantic-segmentation-with-u-net?kernelSessionId=77595813

These identical but separate models both achieved great results. Interestingly, after trying to improve our accuracy and other metrics using a DeepLab v3 model, we found that our initial UNET model was more effective. 

**Code:**

The repo contains three colab notebooks, which contain the code for the project. The notebooks include the data preprocessing, the model building, the train and test sections, and the measurement of metrics. 

1. Object Detection - the UNET object detection model
 
2. Lane Detection - the original UNET model for lane detection

3. Object Detection with Deeplab v3 - The Deeplab v3 model for object detection which did not improve on the performance of the original model

4. Lane Detection with Deeplab v3 - The Deeplab v3 model for lane detection which did not improve on the performance of the original model

Some of the code is specific to our various folders and files, and should of course be changed if used on a local machine. 

If you decide to run this code, we recommend that you purchase increased computing power, from Colab for example, because the code is slow without it. 

**Conclusions:**

We had a number of conclusions at the end of this project:
- Achieving good results can be somewhat straightforward, while achieving great results that can be relevant for the real world is often more difficult
- Image Augmentation is a great way to stretch a dataset further and improve models
- 98% accuracy for a model meant to detect small and unbalanced features sounds good on paper, but practically mean a terrible model. Our first iteration of the lane detection model successfully identified all of the "non lane" features, but missed all of the "lane" features
- Working on a complex project like this can be difficult when done remotely, although having a good leader who can delegate tasks and ensure progress is a key to success (thanks David!)
- Having a good team and working on an interesting problem makes the hard work worth it!

**Authors:**

David Demby 

Samuel Abettan

Akiva Adler
