
Repro to compare different spike detection models on the following metrics

1. Brier score
2. Easy AUC
3. Modfied AUC
4. PR AUC

# Core Idea #
* The Repro is set up like a Kaggle competition
* The Tables folder holds tables for which predictions need to be made
* The Metrics folder holds the files that calculate the metrics



# To run: # 


### 1. create model predictions ###

    1. Bonobo events 
    * create predictions for all event_files in /Tables/testset_bonobo_events.csv 
    * store them in a .csv with columns [event_file,preds] 
    * store the file as /bonobo_pred.csv in in a folder

    2. continious predictions 
    * create predictions for all eeg_files in /Tables/testset_controls.csv 
    * create a folder called /Time_series_pred in the folder where the Bonobo preds are stored
    * store the predictions in this folder using a numpy array of shape [n-steps,]

### 3. Evaluate ###
* Run all scripts in the /Metrics folder 
* Make sure to adapt the model_path at the beginning of each script 
* You will find all results in a results folder at your model_path
