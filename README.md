# Deep Dive into Breast Cancer

About one year ago, I did practise and [worked on](https://github.com/ierolsen/Breast-Cancer-Prediction)   this [dataset](https://www.kaggle.com/uciml/breast-cancer-wisconsin-data). But one year ago I can say I just started the data science therefore I did not know some methods and I never applied before like [NCA](https://scikit-learn.org/stable/modules/neighbors.html#nca), [PCA](https://scikit-learn.org/stable/modules/decomposition.html#pca),etc. 




------------------
### Explanations about Graphs

### 1-) Box Plots
[box_plot_before_stand]
Before applied standardization we draw the box plot graph we can see this graph. 
This means data is not uniform. On the data there are big and small values same columns. Because of that there are long lines on the graph.

[box_plot_after_stand]
After applied standardization we can see this graph.
As you can see this graph looks like more homogeneous, we can see clearly median values and there are not long lines like first one. This is why we use standardization. Big values effect all data. After all model can't learn anything in data. 

### 2-) Pair Plots
[comp. pair_plot]
As you can see standardization doesn't effect pair plot graph. Why?
Because we draw them about their correlation. Skewness is kind of a shape. It doesn't have a correlation between standardization.

### 3-)  Principal Component Analysis (PCA)
[pca_classes]
PCA keeps as much information as possible and reduce the size of data. We used for size transform that from 30 size to 2 size. And after all we'll train our KNN algorithm on this 2 size.
On the graph, you can see kind of a border that seperates 0 and 1. We used for PCA.

if we check out another graph
[pca]
our  ```KNN_Best_Params()``` function determines n_neighbors: 9 as best params. But as we can see our KNN model misclassified.

### 4-)  Neighborhood Components Analysis (NCA)
[nca classes]
Neighborhood Components Analysis is a distance metric learning algorithm which aims to improve the accuracy of nearest neighbors classification compared to the standard Euclidean distance.(from sklearn)

I want to show you something on the graph. maybe you can think model is overfitted but actually not. 

[blue_border]
On this are looks like a overfitting but actually not. 
Our ```KNN_Best_Params()``` function determine n_neighbor:1. Therefore this blue point looked its neighbor and then it create a blue area.



------------------
I need to explain another thing in this project. Because in the notebook you can't understand clearly.
As you can see, after applied NCA Training Acc: 1.0, Test Acc: 0.99. Probably, you can think model is overfitted but actually not because of test acc . If test acc would be about 0.90 we can absolutely say model is overfitted