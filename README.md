# persian_handwritten_classification
Project introduction
This project was created in spring of 2024 in rajaee university as a student group project of Motahare Moghaddam and Fateme Tabasi 
with the aim of collecting Persian handwriting of Iranian cities in order to recognize the handwriting of the names of Iranian cities
The main goal of this project is to create a platform for project development and creating ocr It is Farsi, which is expected in the future actions
The tools used in this project are deep learning algorithms and tensor flow/ keras framework and cnn and rnn networks is

Collection of data sets
It should be noted that data collection was done manually by project programmers
In this way, 436 different handwritings were collected from different people and finally the data set includes 13402 photos of handwritten names of Iranian cities.
In this way, about 16% of men are between the ages of 16 and 22
And about 22% data from women in the age range of 10 to 12
And about 62% of the data is from women in the age range of 16 to 22

Sample data collected:
![p1](https://github.com/motahare-moghaddam/persian_handwritten_classification/assets/174936236/6adc7aef-90f4-4d92-af8e-121277281e3f)




Project stages
1.	data collection
2.	Preprocess the collected data
3.	Building a model to recognize handwritten names of cities
4.	Compare and improve the model
5.	Testing the model

Preprocess the collected data

At first, using the functions defined in the code of the ImageProcessor class , we receive the collected data, which has different angles with the horizon surface and the camera lens, in a clean order to recognize the table.

ImageProcessor input example
![p2](https://github.com/motahare-moghaddam/persian_handwritten_classification/assets/174936236/e3d94aaf-6a47-4c58-92ed-4279fb72d03b)


ImageProcessor output :
![p3](https://github.com/motahare-moghaddam/persian_handwritten_classification/assets/174936236/c09753d0-1bdc-42a6-860d-b86450bce28f)


Then he extracted 31 tables that contain Persian manuscripts of Iranian cities from the table with labels 0 to 30.
In such a way that all the houses in the table with label 0 are integrally the handwriting of a specific and unique city from other labels

Example of cropped house from the table:
![p4](https://github.com/motahare-moghaddam/persian_handwritten_classification/assets/174936236/ffb96dff-fe8d-485f-b4e7-2bdffcaf6cd2)




In the next step, by reading the photos in the 31 labeled folders, numpy presentation We create each image from the input photos along with labels from the onehot presentations, and then we resize (100,50) and transpose the image presentation for the directional reading of the data, which is read and checked horizontally from right to left.

![p5](https://github.com/motahare-moghaddam/persian_handwritten_classification/assets/174936236/0b18a2f9-af67-48f1-83fa-26cd85b019ff)



Building a model to recognize handwritten names of cities

After testing several models and checking validation_accuracy , the optimal final model with 4 convolution layers and 2 LSTM layers was obtained. is
lstm layers due to the fact that lstm has a memory  At each stage of the review and its overall view on the results of the review of the previous stages, the accuracy of the model should be improved



Compare and improve the model
Finally, after 50 epochs, in two stages of 20 and then 30
The accuracy and final loss of the model is as follows
[ loss: 0.6912925839424133, accuracy: 0.900820255279541]
![p6](https://github.com/motahare-moghaddam/persian_handwritten_classification/assets/174936236/27340663-dd62-419c-8859-c94bb14c4403)



Testing the model
To display the test results obtained from the model, we use the test section separated at the beginning of the project, which has not been seen before by the model, so that the final results can be measured in conditions close to reality.
In this section, precision, recall, f1 score and also     The fusion matrix model is displayed for comparison
It should be noted that the numbers 0 to 30 are the labels of 31 cities in the data


Classification Report:
precision recall f 1-score support

0 0.86 0.90 0.88 21
1 0.89 1.00 0.94 25
2 0.88 0.88 0.88 17
3 1.00 0.92 0.96 24
4 0.92 0.81 0.86 27
5 0.88 0.92 0.90 24
6 0.81 0.85 0.83 20
7 0.84 0.94 0.89 17
8 0.78 0.82 0.80 17
9 0.90 0.86 0.88 21
10 0.95 0.95 0.95 19
11 0.94 0.89 0.92 19
12 0.88 0.92 0.90 24
13 0.90 0.79 0.84 24
14 1.00 0.91 0.95 22
15 0.95 0.95 0.95 21
16 1.00 0.84 0.91 25
17 0.77 1.00 0.87 20
18 1.00 0.93 0.96 27
19 0.93 1.00 0.97 28
20 0.93 0.78 0.85 36
21 0.96 0.96 0.96 25
22 0.75 0.82 0.78 22
23 0.94 0.88 0.91 17
24 0.91 0.83 0.87 24
25 0.72 0.93 0.81 14
26 0.70 0.94 0.80 17
27 1.00 1.00 1.00 15
28 0.88 0.92 0.90 25
29 1.00 0.77 0.87 13
30 1.00 0.95 0.98 22

accuracy 0.90 672
macro avg 0.90 0.90 0.90 672
weighted avg 0.91 0.90 0.90 672

Confusion Matrix

![p7](https://github.com/motahare-moghaddam/persian_handwritten_classification/assets/174936236/6b2450a0-6dba-48be-b78c-b119ba5374d4)


Results and future plans
According to the conducted investigations, it shows that the model provides good accuracy for classification on the data due to the limited number of classified data.
In the future plans of this project, it is expected that, while increasing the data available in the dataset, by increasing the accuracy of the pre-process on extracting the table houses and checking the handwritten Persian names of the cities letter by letter by ctc Achieve higher performance accuracy in the future

















