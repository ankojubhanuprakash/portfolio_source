# Classification

## Scaling
We are doing standard scaling!
```python
from sklearn.preprocessing import StandardScaler
def perform_scaling(x,stage):
  scaler1=StandardScaler()
  scaler_filename = "brnd_new_stg"+str(stage)+"_scaler.save"
  joblib.dump(scaler1, scaler_filename) 
  #Load scaler
  #scaler = joblib.load(scaler_filename) 
  return scaler1.fit_transform(x)

#let df.iloc[:,2:-2] stores input fetures
perfrom_scaling(df.iloc[:,2:-2])
```
## Balance classes - (subsampling)
```python

def balance(df):
  balanced=[]
  avlbl_labels=df.labels.unique()## get all labels
  label_counts=df.labels.value_counts() ## calculate  number of samples in each class
  lowest=label_counts.min() ## get the lowest count
  for label in avlbl_labels: ## iterate over all lablels
    if label_counts[label ] > lowest :  ## if label has more number of samples than lowest labels
      balanced.append(df.loc[df.labels==label].sample(n=lowest)) ## sample min datapoionts from this label
    else:
      balanced.append(df.loc[df.labels==label])  

  return pd.concat(balanced, ignore_index=True)

df=balance(df)
```
## Test Train split
```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(df2.iloc[:,:-2],df2.labels, test_size=0.33, random_state=42)
X_train = X_train.values
X_test = X_test.values
y_train = y_train.values
y_test = y_test.values
```
## Knn Model
fit - KNN classifier on the data, and printing classification report 
```python
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report
knn3 = KNeighborsClassifier(n_neighbors = 9).fit(X_train[:,2:], y_train) 
# accuracy on X_test
accuracy = knn3.score(X_test[:,2:], y_test)
print(accuracy) 
# creating a confusion matrix
knn_predictions = knn3.predict(X_test[:,2:])
cm = confusion_matrix(y_test, knn_predictions)
print(cm)
print(classification_report(y_test, knn_predictions))
```
## Error Analysis

Get and save mislabeled datapoints
```python
def save_error(X_test,y_test,predictions,model_num):
  analysis=pd.DataFrame({'predictions':knn_predictions,'Actual':y_test,})
  analysis[['Dir','fname']]=X_test[:,0:2]
  analysis=analysis.loc[analysis.Actual != analysis.predictions,]
  analysis.to_csv('err_analysis_stg'+str(model_num)+'.csv')
save_error(X_test,y_test,predictions=knn_predictions,model_num=1)
```
pending  [Error Analysis](https://techcommunity.microsoft.com/t5/azure-ai-blog/responsible-machine-learning-with-error-analysis/ba-p/2141774)