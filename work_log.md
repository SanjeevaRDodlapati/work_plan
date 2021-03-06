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
  __Note:__ Need to compare with deepcpg_DNA results on the same data (working on it)

### 25 Mar 2020
   1. Ran CpG_Net_Red_LRelu() with combined data - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_29591.out, eval_29668.out
   2. Ran DNA_Module() with AdamW, combined data - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_29592.out
  
  3. Ran DNA_Module()_2L with AdamW, softmin, combined data -/scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_29647.out, eval_29667.out
  4. Transferred CpG data to wahab and renamed .bed files 
### 26 Mar 2020
  1. modified cpgTrain_pytorch.py to add code for cpg position and chrom# tracking.
  2. Also wrote code to collect outputs and write to a file.
  #### ToDo: Remove chrom tracing code in data_generator() function.
  3. Submitted job on modified cpgTrain_pytorch.py file - /scratch/sdodl001/deepcpg/CpG_wgbs/scripts/err_log/eval_30056.out, ./eval_30064.out
  outputs - ./../outputs/results/Combined_Data_26Mar2020
### 27 Mar 2020
  1. wrote code for calculating distance between neighbour cpg
  2. writing code for KNN (not done yet)
### 30 Mar 2020
  1. Changed code for data loading in DNA module.
### 31 Mar 2020 
  1. Implemented DNA module with AdamW, Adam, Sigmoid, Softsign, SGD, dropout
  2. AdamW_LRelu_softsign ./err_log/eval_31408.out
  3. Adam_ReLu_Sigmoid ./err_log/eval_31422.out
### 1 Apr 2020
  1. SGD_Softsign ./err_log/eval_31489.out
  2. SGD_Softsign_do0.5 ./err_log/eval_31501.out
### 2 Apr 2020
  1. Adam_softsign_do0.5 ./err_log/eval_31506.out
  2. Added L1&L2 regularizers __(custome code)__ to DNA module ./err_log/eval_31563.out   ...*__not working__*
  3. Added L2 regularizer __(custome code)__ to DNA module ./err_log/eval_31583.out   ...__*not working*__
  4. Replacing custom L2 regulerizer with the pytorch default ./err_log/eval_31597.out
  5. Submitted DNA module with D7_CTB_S3 cell data to compare with deepcpg_DNA module results on the same data set train chroms - 4, 8, 18, 4, 11, 15, 5, 10, 17, 1, 13, 16, 19, 21, 12, 2 val chroms - 22, 6, 7, X test chrom - 9, 14, 20 ./err_log/eval_31714.out
  6. deepcpg_dna on D7_CTB_S3 cell data - outputs: ./../outputs/results/2Apr2020_D7_CTB_S3_dcpgDNA  - - 
  ./err_log/eval_31726.out
  
### 3 Apr 2020
  1. Ran CpG_Net_LRelu() with knn on combined data - ./../outputs/results/Combined_data_softsign_knn_2Apr2020 -- ./err_log/eval_31734.out __Failed after 2 epochs__
  submitted again - ./err_log/eval_31736.out 
  __Failed after 3 epochs__ submitted again - ./err_log/eval_31791.out(assertion error from BCEloss function)
  __Failed after 2 epochs__ submitted again - ./err_log/eval_31794.out (changed code to address error)
  
  2. deepcpg_dna on combined data - ./err_log/eval_31739.out. ./../outputs/results/3Apr2020_combined_data_dcpgDNA
  3. submitted DNA mdule with combined data - ./err_log/eval_31743.out. - ./../outputs/results/3Apr2020_combined_data_DNA_softsign
  
  ### 8 Apr 2020
   1. Ran CpG_Net_LRelu() with knn on D7_CTB_S13 data with predicted labels- ./err_log/eval_33050.out
   2. Ran CpG_Net_LRelu() with knn on D7_CTB_S13 data with true labels - ./err_log/eval_33060.out
   3. Ran CpG_Net_LRelu() with knn on D7_CTB_S3 data with true labels- ./err_log/eval_33065.out
 ### 9 Apr 2020
   1. Ran CpG_Net_LRelu() with knn on D7_STB_L4 data with true labels- ./err_log/eval_33126.out
   2. Ran CpG_Net_LRelu() with knn on D5_CTB_S2 data with true labels- ./err_log/eval_33127.out
   3. Ran CpG_Net_LRelu() with knn on combined data with Sigmoid (back from Softsign - ./err_log/eval_33152.out
   4. Ran CpG_Net_LRelu() with knn on combined data with Softsign & BCEWithLogitsLoss - ./err_log/eval_33153.out __Failed__
 ### 10 Apr 2020
   1. Ran CpG_Net_LRelu() with knn on combined data with BCEWithLogitsLoss (__NO Simgoid or Softsign__) - ./err_log/eval_33154.out __Failed__,- submitted agian ./err_log/eval_33225.out, ./err_log/eval_33277.out
   
 ### 15 Apr_2020
  1. CpG net with sigmoid, lr 0.001 on D7_CTB_S3 ./err_log/eval_34857.out
  1. CpG net with sigmoid, lr 0.001 on D7_CTB_S13 ./err_log/eval_34859.out
  1. CpG net with sigmoid, lr 0.001 on D7_STB_L4 ./err_log/eval_34860.out
  
### 24 Apr 2020
  1. generated stats(knn, nbrs in 1000bp) for deepcpg paper data. Research/CpG_prediction/Data_Stats/GSE65364_Single_CpG
  2. generated stats for wgbs_human data. Research/CpG_prediction/Data_Stats
  
### 29 Apr 2020
  1. RoadMap_data_stats (knn_acc, auc) calculated. (job ids: 38955, 38960, 38961)
  2. Neighbor count for RoadMap data.(job id: 38799)
  3. Data stats for GSE56879 bisulfite sequence. (job id: 38943) only for two cells
### 30 Apr 2020
  1. Data stats for GSE56879 bisulfite sequence. (job id: 38974, 39270, 39272)
  2. Neighbor count for GSE56879 data.(job id: 39271)
  
### 2 May 2020
  1. Wrote code for binning the data based on neighboring cpg dist.
### 3 May 2020
  1. Wrote code for KNN (k=1) accuracy on binned_data.
### 4 May 2020
  1. Worked on CS895: comp bioinfo class assignmemt and project ppt
### 5 May 2020
  1. Worked on CS895: comp bioinfo class project presentation and report submission. 
### 6 May 2020
  1. Wrote code for DNA seq window extraction. (saved as target-neighbor paired data as hdf5 table)
### 7 May 2020
  1. Changed the code for creating binned data. (earlier code was wrong)
### 8 May 2020
  1. Wrote code for KNN accuracy plots.
  2. Submitted jobs on wahab for dna window extraction on all D3, D5, D7 wgbs_human datasets saved to processed folder. 
 
  
