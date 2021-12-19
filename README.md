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

### How to prepare data
To prepare material data,
First, you should get your own API from The Materials Project databse(https://materialsproject.org/). Then, please write it to the `your-api-key.txt`.
```
python prepare_data.py --input=mp-ids-46744.csv --output=id_prop.csv
```

### How to train
Before you train our model, you should prepare dataset.
```
python main.py --train-ratio 0.6 --val-ratio 0.2 --test-ratio 0.2 data/sample-regression
```

## How to predict
To predict with our pre-trained model,
```
python predict.py dataset_manipulated_pretrained/model_best.pth.tar data/sample-regression
```