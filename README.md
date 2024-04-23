# deep-learning-challenge
Module 21 Challenge - Neural Networks

# Deep Learning Model Analysis Report.

This report presents the development and evaluation of a neural network model designed to predict whether an applicant for funding will be successful in their ventures. This model has been created for the nonprofit foundation Alphabet Soup

## Data Preprocessing

The datastet was read into a pandas DataFrame and the first 5 lines were displayed to identify the target and features data to be used in the neural network. The EIN and NAME columns were identified as candidates for removal as neither target or feature. The target column was identified as the "IS_SUCCESSFUL" column with the remaining columns making up the features for the model. 
After dropping the non-beneficial columns the dataset was analysed to see the number of uniques values in each column. The binning techniques was used on the "APPLICATION_TYPE" and "CLASSIFICATION" columns. Firstly a value count was applied to these columns to determine a cutoff value to reduce the number of unique values all values below the cutoff's were then labelled other.
The categorical data was then converted to numeric using pandas.get_dummies a

## Splitting the Data.

The data was then split into two subsets; a training set and a testing set. The default 75% to 25% train to test split was used.
Finally the datasets were scaled using standard scaler ready for use be the neural network model.

## Model Architecture 
Initial Model.
A tensor flow keras sequential model was selected as the deep learning model with the following parameters;
* Layers - Three layers were initially selected, 
* Neurons - first layer 80, second layer 30, final layer 1,
* Activation Functions - Rectified linear Unit (ReLU) was used for the first two layers and sigmoid was used for the final layer.

ReLU was selected due to the nature of the values in the model possibly being nonlinear. The number of neurons selected for the second layer was less than half of the first layer. Sigmoid was selected for the final layer as a binary feature with only one neuron used.

This model was trained using 100 epochs and then tested for accuracy and loss. The initial model acheived a 72.51% accuracy rating with 56.21% loss. The target accuracy rating was 75% which was not achieved with this initial model.

Increasing Performance.
Three methods were trialled to increase the accuracy score of the model these included dropping columns, increasing the number of nuerons per layer and also increasing the number of layers. Dropping columns resulted in a lower accuracy rating than the initial model of 72.35% compared to 72.51%. Increasing the number of neurons for the first two layers resulted in a marginal increase in accuracy compared to the initial model 72.57% to 72.51%. Adding an additional layer and using the number of neurons from the second trial resulted in another slight increase of 72.61%, however the target 75% was unable to be achieved.
 
## Conclusion.
The deep learning model was unsuccessful in achieving an accuracy of 75% for predicting a succesful campaign, the highest achieved was 72.61%. Further optimisation and experimentation will be necessary to enhance performance in real-world applications.
The final model chosen had four layers, used ReLU optimisation withan initial neuron count of 128 decreasing by half for each successive layer till the final layer of one neuron.

## Recommendations.

Based on the analysis, the following steps could be used to improve the performance of the deep learning model:
* Experiment with different hyperparameters to find the optimal configuration.
* Consider fine-tuning the model architecture or exploring more complex architectures.
* Collect additional data to increase the diversity of the dataset.
* Conduct further analysis to identify any patterns or insights from the model's predictions, using a auto-optimistion tool for example keras tuner.

## References
ChatGPT for creating a callback function
Google help - export model to HDF5 and saving in folder on google drive.
Bootcamp spot learning materials
