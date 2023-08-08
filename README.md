
Repro to compare different spike detection models on the following metrics

1. Brier score
2. Easy AUC
3. Modfied AUC
4. PR AUC

# Core Idea #
* The Repro is set up like a Kaggle competition
* The "Judge" hands out lists of predictions that need to be made
* Each model gets a Folder in the "Backstage" area, where it can work on the tasks. The folder is the only area that is supposed to be modified.
* the task results are sent out to the "Arena", where the evaluation is performed. After the evaluation, the model takes it's evaluation back to the "Backstage" area, where it is stored




# To run: # 

### 0. Init ###
* Create a folder in /Backstage using your_models_name

### 1. create model predictions ###

    1. Bonobo events 
    * create predictions for all event_files in /Judge/testset_bonobo_events.csv 
    * store them in a .csv with columns [event_file,preds] 
    * store the file as /Backstage/your_models_name/bonobo_pred.csv 

    2. continious predictions 
    * create predictions for all eeg_files in /Judge/testset_controls.csv 
    * create the folder /Backstage/your_models_name/Time_series_pred 
    * store the predictions in this folder using a numpy array of shape [n-steps,]

### 3. Evaluate ###
* Run all scripts in the /Arena folder 
* Make sure to adapt the model_path at the beginning of each script 
* You will find all results in /Backstage/your_models_name Results \
* If you have multiple models, you can use /Judge/Comparison.ipynb to compare the models