# Summary of Papers in The Year 2020
## Mar 2929
### 23 Mar 2020

   __Title: Transferrable Prototypical Networks for Unsupervised Domain Adaptation__

   __intro/motivation:__ When source (training) and target (test) datasets have different distributions, machine learning (ML) models learned on source domain do not generalize well to the target domain. Such a problem is known as domain adaptation or transfer learning problem. 
   This issue can be addressed by unsupervised domain adaptiation by aligning source and target data dsitributions or build invariance across domains by minimizing domain shift. 
   
   
   __problem:__


   __solution:__ Proposes transferable prototypical networks (TPN) to explore general-purpose and task-specific domain adaptation by assuming that there exist an embedding space in which samples of each class cluster around a single prototypical (centroid) representation. The classification is done by computing distance to prototype of each lass. 
   
   Matching prototypes of each class in the embeddding space learnt from different domains is general-purpose domain adaptaton. When source and target data are well aligned in the embedding space, target data should be correctly classified by task-specific adaptation by adapting the score distributions of prototype pairs from different domains. 
   
   TPN learns a non-linear mapping of the input examples into domain invariant embedding space. Psuedo labels are assingned unlabeled target data examples by comparing them to each of the prototypes learned from source data. Then, mimimizing the distance between the prototypes of source domain, target domain, and source plus target domain. Task-specific adaptation is achieved by utilizing a softmax over distances of each example to the prototype as the classifier.
     
   __evaluaton:__
   
   
   __contribution__
   

   __questions/comments__
   
   
   __Glossary__
   
   *Maximum Mean Distrepancy* (MMD): 
   
   
   
   
   
   
   
   
   
   
   __Title:__


   __problem:__


   __solution:__
   
   
   __method:__
   
   
   __evaluaton:__
  
  
   __questions/comments__
   
   
   
   
   
   
   __Title:__


   __problem:__


   __solution:__
   
   
   __method:__
   
   
   __evaluaton:__
   
   
   
   __questions/comments__
