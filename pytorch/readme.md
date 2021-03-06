**pytorch\a-process-edf-testtrain.py**
Converts EDF files into parquet files that can be read into the model.
* Requires my custom version of pyedflib: `pip install git+https://github.com/superchordate/pyedflib`
* Selects observations to be in train, validation, and holdout sets.
* Creates data splits.
* Keeps splits of observations together so a split from holdout doesn't get used in training, for example.
* *Idea: split into distinct segments instead of randomly sampling the beginning of each split.*

**pytorch\b-data-loader.py**
Data loaders for the model training to use.

**pytorch\c-model.py**
Model training including defining neural network layers.
* Uses validation data to check generalization, bias/variance.
* *Idea: Try different layers, including other CNN layers or RNN or LSTM*

**pytorch\d-‌holdout-test-rollup.py**
Roll up predictions on splits into a prediction for observations in the holdout set.