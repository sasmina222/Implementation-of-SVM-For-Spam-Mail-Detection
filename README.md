# Implementation-of-SVM-For-Spam-Mail-Detection

## AIM:
To write a program to implement the SVM For Spam Mail Detection.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1.Import the necessary python packages using import statements. 
2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3.Split the dataset using train_test_split. 
4.Calculate Y_Pred and accuracy. 
5.Print all the outputs.
6.End the Program.

## Program:
```
/*
Program to implement the SVM For Spam Mail Detection..
Developed by: sasmina s
RegisterNumber:212225230254
import chardet
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.svm import LinearSVC
from sklearn.pipeline import Pipeline
from sklearn import metrics

file = r"C:\Users\sasmi\Downloads\spam.csv"
with open(file, 'rb') as rawdata:
    result = chardet.detect(rawdata.read(100000))

data = pd.read_csv(r"C:\Users\sasmi\Downloads\spam.csv", encoding='Windows-1252')
x = data["v2"].values
y = data["v1"].values

x_train, x_test, y_train, y_test = train_test_split(x, y, test_size=0.2, random_state=0)

model = Pipeline([
    ('tfidf', TfidfVectorizer()),
    ('clf', LinearSVC())
])

model.fit(x_train, y_train)
y_pred = model.predict(x_test)

accuracy = metrics.accuracy_score(y_test, y_pred)
print(accuracy)
print(metrics.classification_report(y_test, y_pred))
print(metrics.confusion_matrix(y_test, y_pred))
*/
```

## Output:
<img width="483" height="233" alt="image" src="https://github.com/user-attachments/assets/513f6d9c-f6c0-4a9f-8f64-a94868d3ed85" />



## Result:
Thus the program to implement the SVM For Spam Mail Detection is written and verified using python programming.
