## Titanic: Data Analysis and Prediction 

**Project description:** The sinking of the Titanic is one of the most infamous shipwrecks in history.

On April 15, 1912, during her maiden voyage, the widely considered “unsinkable” RMS Titanic sank after colliding with an iceberg. Unfortunately, there weren’t enough lifeboats for everyone onboard, resulting in the death of 1502 out of 2224 passengers and crew.

While there was some element of luck involved in surviving, it seems some groups of people were more likely to survive than others.

In this challenge, we ask you to build a predictive model that answers the question: “what sorts of people were more likely to survive?” using passenger data (ie name, age, gender, socio-economic class, etc).


### Suggest hypotheses about the causes of observed phenomena

We migth have heard and seen a movie about the Titanic before. We also, might have heard that most of adult male passengers did not survived on that night. Why? It was a sacrifice of male passengers, so that, female and younger passengers could survive with lifeboats. It was a mistake that all of lifeboats could not handle 2K of people. It was a tragic and lesson for humanity. However, today I am going to show that what we have heard is around 70% true. Let's see! 


### Assess assumptions on which statistical inference will be based
<iframe src="https://public.tableau.com/views/TitanicDataVisualization_15983899037880/TitanicDashboardKaggleDataset?:embed=yes&:display_count=yes&:showVizHome=no"></iframe>

### Support the selection of appropriate statistical tools and techniques

Train data by SVM
```python
from sklearn import svm
from sklearn.preprocessing import LabelEncoder
from sklearn.metrics import accuracy_score
from sklearn.preprocessing import OneHotEncoder


cols = list(train_data.columns)
X = train_data[['Sex','Age_Band',]].values
y = train_data[['Survived']].values.ravel()

# label Sex and Age_Range to be int!
Le = LabelEncoder()
X[:,0] = Le.fit_transform (X[:,0])
X[:,1] = Le.fit_transform (X[:,1])

X_train, X_test, y_train, y_test = train_test_split(X,y, test_size=0.2)

model = svm.SVC()
model.fit(X_train, y_train)

predictions = model.predict(X_test)
acc = accuracy_score(y_test, predictions)

print("predictions:", predictions)
print("actual: ", y_test)
print("accuracy: ", acc)
```

Train data by Simple Neural Network 
```python
import tensorflow as tf
from tensorflow import keras
from tensorflow.keras.models import Sequential #what is sequential? most simplist type good for one tensor input and output
from tensorflow.keras.layers import Activation, Dense
from tensorflow.keras.optimizers import Adam, SGD
from tensorflow.keras.metrics import categorical_crossentropy

X_train = X_train.astype('float') 
y_train = y_train.astype('float')

model = Sequential([
    Dense(units=16, input_shape=(17,), activation='sigmoid'),
    Dense(units=2, activation='sigmoid')
])

model.compile(optimizer=Adam(learning_rate=0.02), loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(x=X_train, y= y_train,validation_split=0.2, batch_size=15, epochs=60, shuffle=True, verbose=0)

predictions = model.predict(x=X_test
    , batch_size=15
    , verbose=0)

rounded_predictions = np.argmax(predictions, axis=-1)

acc = accuracy_score(y_test, rounded_predictions)

print("predictions:", rounded_predictions)
print("actual: ", y_test)
print("accuracy: ", acc)
```

### Provide a prediction of the test data via the inference 

By SVM
```python
model = svm.SVC()
model.fit(scaled_X, y)

X_test = test_data[['Fare', 'Has_Cabin', 'no_of_fam', 'Age_Band',
       'Sex_0', 'Sex_1', 'Pclass_0', 'Pclass_1', 'Pclass_2', 'Embarked_0',
       'Embarked_1', 'Embarked_2', 'Title_0', 'Title_1', 'Title_2', 'Title_3',
       'Title_4']].values

scaled_X_test = scaler.fit_transform(X_test)

predictions = model.predict(scaled_X_test)

print("predictions:", predictions)
```

By Simple Neural Network
```python
model = Sequential([
    Dense(units=16, input_shape=(17,), activation='sigmoid'),
    Dense(units=2, activation='sigmoid')
])

model.compile(optimizer=Adam(learning_rate=0.02), loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(x=scaled_X, y= y,validation_split=0.2, batch_size=15, epochs=60, shuffle=True, verbose=0)

predictions = model.predict(x=scaled_X_test
    , batch_size=15
    , verbose=0)
rounded_predictions = np.argmax(predictions, axis=-1)

print("predictions:", rounded_predictions)
```

For more details see [Titanic: Data Analysis and Prediction on Kaggle](https://www.kaggle.com/wwongkamjan/titanic-data-analysis-and-prediction/).
