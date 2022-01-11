# Predict the appearence of hypotension during a dialysis session

## The challenge 

## The basis dataset 
* The dataset provided in this repository is based on the dataset created in context of this research paper: "Dataset supporting blood pressure prediction for the management of chronic hemodialysis" https://www.nature.com/articles/s41597-019-0319-8 
* It can be downloaded here: https://figshare.com/articles/dataset/Hemrec_VIP_csv/6260654
### Citation
Lin, CJ., Chen, YY., Pan, CF. et al. Dataset supporting blood pressure prediction for the management of chronic hemodialysis. Sci Data 6, 313 (2019). https://doi.org/10.1038/s41597-019-0319-8

## Creation of the dataset
* Azure Databricks was used to transform the dataset
* The databricks notebook exported to jupyter format can be found in this repository:
  * https://github.com/k-weide/dialysis_hypotension_prediction_challenge/blob/main/create_dataset_with_databricks.ipynb 
*  It includes some explanation how and why dataset was derived from the basis dataset the way it is done

## Some other interesting information
* There is a product by B. Braun dealing with the challenge of hypotension during dialysis as well by using Fuzzy Logic
  * https://www.bbraun.com/en/products/b0/biologic-rr-comfort.html
  * Research paper regarding this can be found here: https://academic.oup.com/ndt/article/22/5/1420/1922750 
