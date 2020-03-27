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
  1. wrote code for class weights (calculated batchwise instead of chromosome-wise)
  1. Plotted gradient flow for bothe CpG.Net and deepcpg_DNA models

### 3 Mar 2020
  1. Batch normalization on conv layers of  CpG.Net() model is not working. 

### 4 Mar 2020
  1. Ran cpgTrain_pytorch with CpG_Net_Reduced() model with Adam optimizer- loss reduced from around 6 to around 0.25 and stabilized. 
  2. With SGD optimizer, loss is not at all reducing. Gradient flow plot shows almost 0 gradient flow.
  3. With ASGD optimizer also not working
  
### 5 Mar 2020
  1. Leaky ReLU is also tested with reduced cpg_net.  - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_25521.out
  Results - /scratch/sdodl001/deepcpg/CpG_wgbs/outputs/results/AdamW_lr0.0001_5Mar2020
### 6 Mar 2020
  1. SGD_Nesterov optimizer with CpG.Net() - Desktop\Research\CpG_prediction\outputs\results\sgd_nesterov
    
   learning curves - Desktop\Research\CpG_prediction\outputs\results\training_metrics_sgd_nesterov.pdf
   
   Other learning curves - Desktop\Research\CpG_prediction\outputs\results
   
  2. Variable learning rate, CpG.Net() - Output - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_25529.out
  Results - /scratch/sdodl001/deepcpg/CpG_wgbs/outputs/results/AdamW_lr0.0001v_LReLU_6Mar2020

### 9 Mar 2020
  1. Submit jobs with CpG.Net_Red_LRelu(), 100 and 150 epochs
  
### 10 Mar 2020
  #### ToDO:
  1. Change the code for multiple cell data input
  2. Write code for evaluation of CpG.Net()
### 23 Mar 2020
  1. Variable learning rate on deepcpg_DNA_Module() - output - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_29532.out

  __NOTE:__ DNA_Module() gradients are not backpropogating. No improvement in loss (stable around 0.32 from the beginning).

### 25 Mar 2020
   1. Ran CpG_Net_Red_LRelu() with combined data - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_29591.out, eval_29668.out
   2. Ran DNA_Module() with AdamW, combined data - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_29592.out
  
  3. Ran DNA_Module()_2L with AdamW, softmin, combined data -/scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_29647.out, eval_29667.out
  4. Transgered CpG data to wahab and renamed .bed files 
### 26 Mar 2020
  1. modified cpgTrain_pytorch.py to add code for cpg position and chrom# tracking.
  2. Also wrote code to collect outputs and write to a file.
  #### ToDo: Remove chrom tracing code in data_generator() function.
  3. Submitted job on modified cpgTrain_pytorch.py file - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_30056.out, ./eval_30064.out
  outputs - ./../outputs/results/Combined_Data_26Mar2020
