# Prediction-of-Magnetic-Properties-using-CGCNN

## Requirements
This package requires:
* Pytorch
* scikit-learn
* pymatgen

To prepare material data, there are some additional requirements:
* requests
* tqdm
* click

## How to train
Since it is impossible to upload all data to github, to reproduce the training the data set should be downloaded with prepare_data.py and used for training. 
### How to prepare data
First, you should get your own API from The Materials Project databse(https://materialsproject.org/). Then, please write it to the `your-api-key.txt`.
To prepare material data,
```
python prepare_data.py --input=mp-ids-46744.csv --output=id_prop.csv
```

### How to train
Before you train our model, you should prepare dataset.
```
python main.py --train-ratio 0.6 --val-ratio 0.2 --test-ratio 0.2 data/sample-regression
```

## How to predict
We provide some good performance samples. Use prediction.py as a sample prediction
To predict with our pre-trained model,
```
python predict.py dataset_manipulated_pretrained/model_best.pth.tar data/sample-regression
```
