# Melanoma Image Augmentation and classification

Skin cancer is the most prevalent type of cancer. Melanoma, specifically, is responsible for 75% of skin cancer deaths. An early and accurate detection can make treatment more effective. This repository deals with detecting Melanoma using skin lesion images. The highly imbalanced SIIM-ISIC Melanoma Classification dataset containing 'benign' and 'malign' samples has been used. To tackle the class imbalance, CycleGANs have been used to generate synthetic 'malign' samples.

![image](https://user-images.githubusercontent.com/49569284/141083557-636b7464-bc2d-4552-802c-e5950286145f.png)

Melanoma detection is a binary classification problem with two classes, 'benign' and 'malign.' The dataset has around 33,000 'benign' samples and only 584 'malign' samples. In addition, there are around 10,000 test samples. Deep Learning models are biased towards majority class. Oversampling of minority class image samples using data augmentation becomes essential. CycleGANs is a variant of GAN which performs image to image translation. Pairs of 'benign' and 'malign' samples are fed into the model and it learns to transform 'benign' samples to 'malign' samples and vice versa. Using the CycleGAN generated new samples, the dataset is balanced. A binary classifier is trained by fine-tuning EfficientNet weights. The perfomance of CycleGAN-based data augmentation has been compared with traditional data augmentation (rotation, flipping, random-cropping) techniques.

GAN was trained for 720 epochs with an initial learning rate of 0.0002. After generating synthetic ‘malign’ samples, a total of around 32,000 ‘malign’ were available, thereby balancing the dataset. Now, the pre-trained EfficientNet weights were tuned for the binary classification task and tested on test set of around 10,000 images. No additional data augmentation was performed here. Fig.1 shows some of the synthetic 'malign' samples generated from 'benign' samples using the proposed methods. Label smoothing was introduced so as to improve the quality of images generated. Comparison analysis for different methods for data augmentation has been shown in the give table.

|            Method            	| Test ROC AUC 	|
|:----------------------------:	|:------------:	|
| Flipping, Cropping, Rotating 	|     0.83     	|
|       CycleGAN baseline      	|     0.87     	|
|   CycleGAN label smoothing   	|     0.89     	|

Output -

![](https://github.com/sm823zw/Melanoma-Image-Augmentation-and-classification/blob/main/Images/output.png)

Loss plot (first 360 epochs only) - 


![](https://github.com/sm823zw/Melanoma-Image-Augmentation-and-classification/blob/main/Images/lossplot_label_smoothing.png)

Example of synthetic generated malign samples -


<img src="https://github.com/sm823zw/Melanoma-Image-Augmentation-and-classification/blob/main/Images/generated_malign.png" alt="drawing" width="500"/>
