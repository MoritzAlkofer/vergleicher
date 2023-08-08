Repro to compare different spike detection models on the following metrics

1. Brier score
2. Easy AUC
3. Modfied AUC
4. PR AUC

To run:

0. Create a folder in /Backstage using your_models_name

1. create model predictions

    1. create predictions for all event_files in /Judge/testset_bonobo_events.csv
    
    store them in a .csv with columns [event_file,preds]
    
    store the file as /Backstage/your_models_name/bonobo_pred.csv

    2. create continious predictions for all eeg_files in /Judge/testset_controls.csv 
    
    create the folder /Backstage/your_models_name/Time_series_pred
    
    store the predictions in this folder using a numpy array of shape [n-steps,]

3. Evaluate
   Run all scripts in the /Arena folder
   Make sure to adapt the model_path at the beginning of each script
   You will find all results in /Backstage/your_models_name Results
   If you have multiple models, you can use /Judge/Comparison.ipynb to compare the models