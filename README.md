# Brain-Tumor-detection
The tumor is the growth abnormal cells in the various part of the body. Here we deal with tumors in the brain. The tumors consist of differnt types they can  noncancerous (benign) and cancerous (malignant). These are the basic classification further they can be divided on the body part they occur example gloima . It generally occurs in the brain and spinal cord. The glioma is further divided into sub-region such as  necrosis,edema, enhancing and non-enhancing region. You can read more here https://en.wikipedia.org/wiki/Glioma. The detection of the tumor is quite difficult as the contain only small part of the brain which convert this problem into imbalanced dataset problem. I have used U-net for the classification. We divided the problem into of tumor detection into two parts 1. Segmentation of tumor 2. Classifying the sub-region.
![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Glioma-sub-regions-The-image-patches-show-from-left-to-right-the-whole-tumor-yellow.ppm)
imagesource(https://arxiv.org/pdf/1811.02629.pdf)


# Dataset
Here we used Brats dataset you can find it here http://braintumorsegmentation.org/. The dataset is consist of 369 3D images of size 240 x 240 x 155. Leave some initial and last images of each image as they are blank. Some example are here.
![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Braintumor%20(2).jpg)  ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Braintumor%20(3).jpg)  ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Braintumor%20(4).jpg)   ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Braintumor%20(5).jpg)

# Step to follow:
1. The image is in the form of .nii.gz form so I used nibabel library to load the images.
2. The noise in the image can be cancelled using the median filter or non_local means technique.
3. The images than feed to the the U-Net the architecture can be seen in the figure. The U-net is robust to generate the segmented images by using the current features maps of image and the previously create feature maps. As shown in the architecture.

![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/The-architecture-of-Unet.ppm)
 
 # Result
 There are two results 1. Segmentation of tumor 2. classification of sub-region
    
   1 Segmentation of tumor
    
![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Brain.png)  ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/groundtruth.png)   ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/predicted.png)

         Brain image                             GroundTruth                         Predicted
    
   2 Classification of sub-region
    
 ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Brain.png)  ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Truthimage.png)   ![](https://github.com/BhaveshRaj27/Brain-Tumor-detection/blob/main/Images/Predictedother.png)
       
         Brain image                             GroundTruth                         Predicted
