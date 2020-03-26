# Summary of Papers - Mar 2020
### 23 Mar 2020

   __Title: Transferrable Prototypical Networks for Unsupervised Domain Adaptation__ (https://arxiv.org/pdf/1904.11227.pdf)

   __intro/motivation:__ 
   
  
   __problem:__
   
   When source (training) and target (test) datasets have different distributions, machine learning (ML) models learned on source domain do not generalize well to the target domain. Such a problem is known as domain adaptation or transfer learning problem. 
   This issue can be addressed by unsupervised domain adaptiation by aligning source and target data dsitributions or build invariance across domains by minimizing domain shift.


   __solution:__
   
   Proposes transferable prototypical networks (TPN) to explore general-purpose and task-specific domain adaptation by assuming that there exist an embedding space in which samples of each class cluster around a single prototypical (centroid) representation. The classification is done by computing distance to prototype of each lass. 
   
   Matching prototypes of each class in the embeddding space learnt from different domains is general-purpose domain adaptaton. When source and target data are well aligned in the embedding space, target data should be correctly classified by task-specific adaptation by adapting the score distributions of prototype pairs from different domains. 
   
   ![TPN](https://github.com/SanjeevaRDodlapati/work_plan/blob/master/Images/TPN.png)
      
   TPN learns a non-linear mapping of the input examples into domain invariant embedding space. Psuedo labels are assingned unlabeled target data examples by comparing them to each of the prototypes learned from source data. Then, mimimizing the distance between the prototypes of source domain, target domain, and source plus target domain. Task-specific adaptation is achieved by utilizing a softmax over distances of each example to the prototype as the classifier.
   
   TPN is trained by reducing multi-granular domain discrepancy at class-level and sample-level. Class level descrepancy is reduced by learning similar prototypes of each class in different domains. Sample-level discrepancy is learned by enforcing similar score distributions across prototypes of different domains. Each trining iteration proceeds by performing above two steps alternately.   
     
   __evaluaton:__
   
   trained and evaluated 4 digits image datasets: MNIST, USPS, SVHN, and VisDA. 
   classification accuracies calculated on M-to-U, U-to-M, S-to-M, synthetic to real on VisDA. Compared to various reported methods such as RevGrad, DC, DAN, RTN, ADDA, JAN, MCD. 
   
   
   __contribution__
   
   TPN -  

   __questions/comments__
   
   
   __Glossary__
   
   *Maximum Mean Distrepancy* (MMD):a non-parametric metric for the comparisons between the distributions of source and target domains
   *kernel Hilbert space*: 
   
   
   
 ### 24 Mar 2020  
   
   __Title:Synergistic Image and Feature Adaptation: Towards Cross-Modality Domain Adaptation for Medical Image Segmentation__ (https://arxiv.org/abs/1901.08211)


   __Intro/motivation:__
   
   
   __Problem:__


   __Solution:__
   
   
   __Evaluaton:__
   
   
   __Contributions:__
  
  
   __Questions/comments__
   
   
   
 ### 24 Mar 2020  
   
   __Title:FCNs in the Wild: Pixel-level Adversarial and Constraint-based Adaptation__ (https://arxiv.org/abs/1612.02649)


   __Intro/motivation:__ Understanding an image at pixel level is known as semantic segmentation. It is widely used in computer vision machine learning applications for object detection.It has many applocations in medical image segmentation and autonomous driving and other similar tasks.
   
   
   __Problem:__ Adaptation to new domain is difficult becasuse of domain shift issues arising out of differences in data distribution of source and target domain.


   __Solution:__
   Proposes an unsupervised domain adaptive semantic segmentation method to pixel prediction problem. This method consists of global and category specific techniques. 
   
   __Evaluaton:__
   
   
   __Contributions:__
  
  
   __Questions/comments__
   
   
   
 ### Data:  24 Mar 2020
   
   __Title: Deep learning enables cross-modality super-resolution in fluorescence microscopy__ (https://www.nature.com/articles/s41592-018-0239-0)


   __Intro/motivation:__ High resolution microscopy images allow observe minute details and inner workings of various biological processes of a cell. However, resolution depends on several factors such as oiptical setups, fluorophores, mounting media, and post-processing computations. 
   
   
   __Problem:__ Low resolution of microscopy images


   __Solution:__ GAN to achieve super resolution and cross-modality image transformations using matched pairs of experimentally acquired low-and higher-resolution images. 
   Demonstrated on wide-field, confocal, and TIRF microspoes. 
   
   Wide-field: 
   used multi-stage image registration process to accurately align 2,625 pairs of low- and high-resolution image patches.
   Trained a separate model for each filter set, and results were compared with ground truth.
   A pretrained DNN was applied to each color channel of the input images and achieved good agreement with ground truth.
   Also noticed that network output images display sharper details than ground truth image.
   Model trained on images captures with TxRed filterset was able to perform well even on images that were captured using different filter sets - DAPI and FITC. 
   
   Cross-modality - from confocal to STED:
   STED were recored with 3 to 10 fold stronger excitation power than confocal. 
   Network trained on lwo resolution confocal images takes confocal test image and outputs an image that matched the STED image of the same sample.
   Measure the PSFs arising from the images of single/isolated nano-beads across the smaple FOV
   Also improved SNR (supplimentary note 6)
   Applied to super-resolve Histone 3 distributions within fixed HeLa cell nuclie.
   Made use of tranfer learning by training with nano particles and applied to resolve cell nuclie using confocal to STED transformation.
   Transfer learning also speeds up the training process (methods)
   
   Cross-modality from TIRF to TIRF-SIM:
   Trained on gene-edited SUM159 cell expressing eGFP-labeled claritin adpator AP2, and blindly tested its inference. 
   Network was able to detect the dissociation of clathrin-coated pits from larger clathrin patches. 
   Also applied to aminoserosa tissues of Drosophila embryos, highly motile clathrin-coated structures can be clearly distinguished.
   
   Depth of field enhancement:
   
   Artifact analysis:
   
   Methods:
   GAN - two regularization terms (MSE & SSIM index)
   Generator - Unet based CNN - 4 downsampling and 4 upsamplig blocks. Each downsampling block consists of 3 residual convolutional blocks, LRelu, average pooling afer each conv layer. Upsampling block consists of 3 conv blocks.
   
   Discriminator - conv layer followed by 5 conv blocks. output of the last conv block fed into avg pooling, followed by 2 fully connected layers for dimension reduction. The last layer is a sigmoid. 
   
   Training - patch size of 64 x 64, batch size 12, random initialization, Adam, lr = 0.0001 & 0.00001 respectively for gen and discriminator. Tensorflow 1.7
   
   __Evaluaton:__
   
   
   __Contributions:__
  
  
   __Questions/comments__


 ### Date: 25 Mar 2020  
   
   __Title: RNAcommender: genome-wide recommendation of RNA–protein interactions__ (https://academic.oup.com/bioinformatics/article/32/23/3627/2525632)


   __Intro/motivation:__ 
   RNA-protien interactions play vital role in RNA regulatory processes. 
   
   
   __Problem:__ 
   Need to develop methods to determine RNA-protien interations


   __Solution:__ 
   Presents RNAcommender - recommends unexplored RNA targets to RNA binding proteins. 
   
   
   __Evaluaton:__
   
   
   __Contributions:__
  
  
   __Questions/comments__


 ### Date:  26 Mar 2020
   
   __Title: Limited correspondence in visual representation between the human brain and convolutional neural networks__ (https://www.biorxiv.org/content/10.1101/2020.03.12.989376v1)


   __Intro/motivation:__
   
   
   __Problem:__ 



   __Solution:__
 
   
   
   __Evaluaton:__
   
   
   __Contributions:__
  
  
   __Questions/comments__









 ### Date:  
   
   __Title: __


   __Intro/motivation:__
   
   
   __Problem:__


   __Solution:__
   
   
   __Evaluaton:__
   
   
   __Contributions:__
  
  
   __Questions/comments__
