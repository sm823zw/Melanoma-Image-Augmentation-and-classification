# Melanoma Image Augmentation and classification

Skin cancer is the most prevalent type of cancer. Melanoma, specifically, is responsible for 75% of skin cancer deaths. An early and accurate detection can make treatment more effective. This repository deals with detecting Melanoma using skin lesion images. The highly imbalanced SIIM-ISIC Melanoma Classification dataset containing 'benign' and 'malign' samples has been used. To tackle the class imbalance, CycleGANs have been used to generate synthetic 'malign' samples.

Melanoma detection is a binary classification problem with two classes, 'benign' and 'malign.' The dataset has around 33,000 'benign' samples and only 584 'malign' samples. In addition, there are around 10,000 test samples. Deep Learning models are biased towards majority class. Oversampling of minority class image samples using data augmentation becomes essential. CycleGANs is a variant of GAN which performs image to image translation. Pairs of 'benign' and 'malign' samples are fed into the model and it learns to transform 'benign' samples to 'malign' samples and vice versa. Using the CycleGAN generated new samples, the dataset is balanced. A binary classifier is trained by fine-tuning EfficientNet weights. The perfomance of CycleGAN-based data augmentation has been compared with traditional data augmentation (rotation, flipping, random-cropping) techniques.

Loss plot - 


![](https://github.com/sm823zw/Melanoma-Image-Augmentation-and-classification/blob/main/Images/lossplot.png)
