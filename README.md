# Deep Dive into Breast Cancer

About one year ago, I did practise and [worked on](https://github.com/ierolsen/Breast-Cancer-Prediction)   this [dataset](https://www.kaggle.com/uciml/breast-cancer-wisconsin-data). But one year ago I can say I just started the data science therefore I did not know some methods and I never applied before like [NCA](https://scikit-learn.org/stable/modules/neighbors.html#nca), [PCA](https://scikit-learn.org/stable/modules/decomposition.html#pca),etc. 




------------------
### Explanations about Graphs

### 1-) Box Plots
![box_plot_before_stand](https://user-images.githubusercontent.com/30235603/77831648-7e0fd080-7141-11ea-9d80-4f68fd7de3f5.png)
Before applied standardization we draw the box plot graph we can see this graph. 
This means data is not uniform. On the data there are big and small values same columns. Because of that there are long lines on the graph.

![box_plot_after_stand](https://user-images.githubusercontent.com/30235603/77831654-8a942900-7141-11ea-86c5-39a9a4cc50af.png)
After applied standardization we can see this graph.
As you can see this graph looks like more homogeneous, we can see clearly median values and there are not long lines like first one. This is why we use standardization. Big values effect all data. After all model can't learn anything in data. 

### 2-) Pair Plots
![comp  pair_plot](https://user-images.githubusercontent.com/30235603/77831664-9e3f8f80-7141-11ea-9388-dcb150f8530c.png)
As you can see standardization doesn't effect pair plot graph. Why?
Because we draw them about their correlation. Skewness is kind of a shape. It doesn't have a correlation between standardization.

### 3-)  Principal Component Analysis (PCA)
![pca_classes](https://user-images.githubusercontent.com/30235603/77831676-ac8dab80-7141-11ea-8344-7a95f26d2183.png)
PCA keeps as much information as possible and reduce the size of data. We used for size transform that from 30 size to 2 size. And after all we'll train our KNN algorithm on this 2 size.
On the graph, you can see kind of a border that seperates 0 and 1. We used for PCA.

if we check out another graph
![pca](https://user-images.githubusercontent.com/30235603/77831696-bc0cf480-7141-11ea-8e06-6b27cb8b4f41.png)
our  ```KNN_Best_Params()``` function determines n_neighbors: 9 as best params. But as we can see our KNN model misclassified.

### 4-)  Neighborhood Components Analysis (NCA)
![nca classes](https://user-images.githubusercontent.com/30235603/77831703-c6c78980-7141-11ea-9dcf-1b9f0bfb4409.png)
Neighborhood Components Analysis is a distance metric learning algorithm which aims to improve the accuracy of nearest neighbors classification compared to the standard Euclidean distance.(from sklearn)

![nca](https://user-images.githubusercontent.com/30235603/77831744-01312680-7142-11ea-825f-5ec806a58695.png)
nca classify clearly

I want to show you something on the graph. maybe you can think model is overfitted but actually not. 

![blue_border](https://user-images.githubusercontent.com/30235603/77831715-d3e47880-7141-11ea-919e-911bca7e9067.png)
On this are looks like a overfitting but actually not. 
Our ```KNN_Best_Params()``` function determine n_neighbor:1. Therefore this blue point looked its neighbor and then it create a blue area.

This is the model evaluation graph:
![model_evaluation](https://user-images.githubusercontent.com/30235603/77831760-173ee700-7142-11ea-87d2-157c1b02936c.png)


------------------
I need to explain another thing in this project. Because in the notebook you can't understand clearly.
As you can see, after applied NCA Training Acc: 1.0, Test Acc: 0.99. Probably, you can think model is overfitted but actually not because of test acc . If test acc would be about 0.90 we can absolutely say model is overfitted
