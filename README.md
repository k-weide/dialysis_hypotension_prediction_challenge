# Predict the appearence of hypotension during a dialysis session
## The challenge 
* Please choose **either** Version A or B 
* Do an **exploratory data analysis** with the corresponding dataset
  * Version A - dialysis_dataset.csv
  * Version B - dialysis_dataset_minutes_to_hypotension.csv
* Do *some research* for the functional domain 
  * A starting point can be found in this README
* **Try** to **create a machine learning model** 
  * Version A - Classify the column "class" in class "hypotension_is_coming" or class "no_hypotension_in_sight"
  * Version B - Predict the "minutes_to_first_hypotension" as analogy to RUL (Remaining Useful Life) in Predictive Maintenance
* Prepare an **maximum 15 minutes presentation**
  * Results of exploratory data analysis
  * What did you learn about the domain of hemodialysis
    * expecially in context of hypotension and the dataset
  * Which approach did you use for creating the machine learning model
    * And why did you choose it ? 
  * Results of machine learning model and interpretation of results
    * **In general it is totaly fine if the model delivers bad performance as long as you can show and explain your approach** 
  * Challenges faced during the analysis and model creation

### Version A - Classification
In **dialysis_dataset.csv** you will find bloop pressure measurements that were taken during a hemodialysis session and additional information like parameters of the dialysis machine - like the ultrafiltration rate - and parameters of the patient information system (PIMS) like for example the age, gender, the weight before starting the treatment or the dry weight which is the target weight after the dialysis. 

For details about the data please look in "Creation of the dataset" in this README where you will find the corresponding notebook and additionally please read the paper mentioned in "The basis dataset" in this README and the other information available in this README are helpful as well. 

In the column class of the dataset you will find two values: 
* hypotension_is_coming
  * This means that after this measurement there will be a hypotension in 60 to 15 minutes
* no_hypotension_in_sight
  * This means that during the dialysis session there will be no hypotension at all or not in the next 60 minutes

The challenge is to create a machine learning model that can classify if an entry is either in class "hypotension_is_coming" or class "no_hypotension_in_sight"

### Version B - Analogy to Predictive Maintenance
In **dialysis_dataset_minutes_to_hypotension.csv** you will find bloop pressure measurements that were taken during a hemodialysis session and additional information like parameters of the dialysis machine - like the ultrafiltration rate - and parameters of the patient information system (PIMS) like for example the age, gender, the weight before starting the treatment or the dry weight which is the target weight after the dialysis. There are two differences to the Version A dataset:
* You have three more columns: "hypotension_in_session", "minutes_to_first_hypotension", "minutes_to_dialysisend"
* The dataset is filtered with "hypotension_in_session" = True which means that **in all sessions of the dataset a hypotension appeared** while in Version A there are sessions where never hypotension appeared

The approach for Version B of this challenge is to use an analogy to the "NASA Turbofan engine degradation simulation data set" (https://ti.arc.nasa.gov/tech/dash/groups/pcoe/prognostic-data-repository/#turbofan). This dataset is very well known from the domain of predictive maintenance and there are a lot of tutorials and publications like for example:
* https://www.kaggle.com/behrad3d/nasa-cmaps
* https://towardsdatascience.com/predictive-maintenance-of-turbofan-engines-ec54a083127
* https://4cda.com/intro-to-predictive-maintenance-on-nasa-turbofan-engine-dataset-using-machine-learning/

At NASA Turbofan one approach is to predict the RUL (Remaining Useful Live) of a turbofan engine. As analogy for our dataset this would mean to predict the "minutes_to_first_hypotension" for a dialysis session.

### Details about the data
For details about the data please look in "Creation of the dataset" in this README where you will find the corresponding notebook and additionally please read the paper mentioned in "The basis dataset" in this README and the other information available in this README are helpful as well. 

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

## Similar research papers 
* "Intelligent system to predict intradialytic hypotension in chronic hemodialysis"
  * https://www.sciencedirect.com/science/article/pii/S0929664618302584
* "Predicting the Appearance of Hypotension During Hemodialysis Sessions Using Machine Learning Classifiers" 
  * https://pubmed.ncbi.nlm.nih.gov/33671029/

## Some other interesting information
* There is a product by B. Braun dealing with the challenge of hypotension during dialysis as well by using Fuzzy Logic
  * https://www.bbraun.com/en/products/b0/biologic-rr-comfort.html
  * Research paper regarding this can be found here: https://academic.oup.com/ndt/article/22/5/1420/1922750 
* A well written information for dialysis patients (in German)
  * http://www.dialyse-la.de/download/patienteninformation.pdf
