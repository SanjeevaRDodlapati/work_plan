# Daily Wrok LogBook

### Jan 30, 2020
  1. added l2 regularization term to cpgTrain_pytorch.py
  2. Created a separate file deepcpg_DNA_Train_pytorch.py
  
  #### To Do:
  + *run deepcpg DNA module for D7_CTB_S3 and compare loss with deepcpg_DNA_Train_pytorch.py*
  + *modify cpgTrain_pytorch.py to run multipul cell data*
  + *save model on val loss*
  + *write code for learning curves*
  + *write code for KNN for predictions*
  + *write code for label weights*
  + *push code to github*

  ##### statue update:
  + ~~run deepcpg DNA module for D7_CTB_S3 and compare loss with deepcpg_DNA_Train_pytorch.py*~~ : Done
  + *modify cpgTrain_pytorch.py to run multipul cell data*
  + ~~save model on val loss*~~ : Done
  + *write code for learning curves*
  + *write code for KNN for predictions*
  + *write code for label weights*
  + ~~push code to github*~~: Could not be done
### Jan 31, 2020
+ Written code for learning curves 
+ Group Meeting
+ First pass read [Assessing the impact of generative AI on medicinal chemistry](https://www.nature.com/articles/s41587-020-0418-2#article-info)
+ First pass read [Deep learning enables rapid identification of potent DDR1 kinase inhibitors](https://www.nature.com/articles/s41587-019-0224-x#article-info)

### Feb 26, 2020
  + Checked deepcpg code for class weights and other parameters
  
### 27 Feb 2020
To DO:
  1. wrote code for class weights (calculated batchwise instead of chromosome-wise)
  1. Plotted gradient flow for bothe CpG.Net and deepcpg_DNA models
### 4 Mar 2020
  1. Ran cpgTrain_pytorch with CpG_Net_Reduced() model with Adam optimizer- loss reduced from around 6 to around 0.25 and stabilized. 
  2. With SGD optimizer, loss is not at all reducing. Gradient flow plot shows almost 0 gradient flow.
  3. With ASGD optimizer also not working
  
### 5 Mar 2020
  1. Leaky ReLU is also tested with reduced cpg_net. Results - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_25521.out
