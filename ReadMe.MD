# Image classification on the histpathology dataset
## Description
Building machine learning model to classify based on the image data as cancerous or not cancerous as well as classify based on cell type (fibroblast, inflammatory,epithelial, etc.)

## Data 
CRCHistoPhenotypes dataset. The dataset consists of 27x27 RGB images of cells from 99 different patients

### Data Exploration
After Exploring through the data it was observed that the data was imbalanced towards non cancerous and Majority of the data contained epithelial cells. Also observed that in this dataset all epithelial cells were cancerous.

### Data Preprocessing
The Data was checked for missing data and whether there were any data entry errors present in the name of the classes. The InstanceID data was dropped as it was non relevant to the model. As we are dealing with image data the size and colour channel of all images were checked to see whether they are the same. They all were of size 27X27 and RGB color channel.

### Data Splitting
The main dataset was randomly split into train, validation, and test sets to avoid any types of bias in the model. The test set is 20% of the dataset, and the remaining data is divided into an 80/20 train/validation split. The test set is used to evaluate model performance.

## Evaluation Metrics
For both cancer detection and cell type classification, our models are evaluated using metrics such as accuracy, precision, recall, and f1 score on the test set. In addition, we also consider the training time to ensure that the model is scalable for larger datasets. Also for cancerous we gave more emphasis towards recall as a person with cancer getting classed as non cancerous is more dangerous than the other way around.

## Model selection and tuning
MLP was selected because it is a traditional neural network which is a good baseline model to base investigations on, LeNet CNN was used as it is a simple CNN model and as our images in the data was only 27X27 as it works well with small images. Each model was iteratively tuned for hyperparameter by changing the number of layers and units, introducing dropouts and regularization, finetuning the model

## Result 
The LeNet CNN model performed better for the cancerous and cell type classification
- Cancer detection: LeNet CNN Model with increased kernel and pooling size also reduced number
of filters which provided with an accuracy of 88%, recall 0.76, F1 score 0.81, AUC score 0.85
- Cell classification: LeNet CNN Model with learning rate set 0.001, along with data augmentation which provided the
result of accuracy of 76%, Recall 0.757, F1 score 0.757 and AUC score 0.895.

