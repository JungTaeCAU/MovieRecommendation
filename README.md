<div align=center>

#  Movie Recommendation System with Kaggle 

<img src="https://img.shields.io/badge/JupyterNotebook-F37626?style=flat-square&logo=Jupyter&logoColor=white"/>
<img src="https://img.shields.io/badge/VSCODE-007ACC?style=flat-square&logo=VisualStudioCode&logoColor=white"/>
<img src="https://img.shields.io/badge/Kaggle-20BEFF?style=flat-square&logo=Kaggle&logoColor=white"/>
 <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=Streamlit&logoColor=white"/>



[link]: https://www.kaggle.com/code/ibtesama/getting-started-with-a-movie-recommendation-system/notebook

This Project is based on [Kaggle][link]


 </div>

How to Run
=============
Requirements
-------------
This project was built in VSCode.
* [VSCode](https://code.visualstudio.com/)
* [Jupyter-Notebook](https://jupyter.org/)

Clone this repo
-------------
    git clone https://github.com/JungTaeCAU/MovieRecommendation.git
Run in Local
-------------
1. install streamlit library
<pre>
<code>
$ pip install streamlit
</code>
</pre>
2. install tmdbv3api library
<pre>
<code>
$ pip install tmdbv3api
</code>
</pre>
3. RUN
<pre>
<code>
$ streamlit run app.py
</code>
</pre>

Demographic Filtering
-------------
Before getting started with this -

* we need a metric to score or rate movie
* Calculate the score for every movie
* Sort the scores and recommend the best rated movie to the users.
We can use the average ratings of the movie as the score but using this won't be fair enough since a movie with 8.9 average rating and only 3 votes cannot be considered better than the movie with 7.8 as as average rating but 40 votes. So, I'll be using IMDB's weighted rating (wr) which is given as :-

![image](https://user-images.githubusercontent.com/37211139/186607756-d71ba895-7e69-4cd7-92ba-0b43b20fec1d.png)

where,

* v is the number of votes for the movie;
* m is the minimum votes required to be listed in the chart;
* R is the average rating of the movie; And
* C is the mean vote across the whole report

Content Based Filtering
-------------
We see that over 20,000 different words were used to describe the 4800 movies in our dataset.

With this matrix in hand, we can now compute a similarity score. There are several candidates for this; such as the euclidean, the Pearson and the cosine similarity scores. There is no right answer to which score is the best. Different scores work well in different scenarios and it is often a good idea to experiment with different metrics.

We will be using the cosine similarity to calculate a numeric quantity that denotes the similarity between two movies. We use the cosine similarity score since it is independent of magnitude and is relatively easy and fast to calculate. Mathematically, it is defined as follows:

![image](https://user-images.githubusercontent.com/37211139/186608064-2a776901-4d78-4d3c-998b-7ae80f6ef39d.png)

Since we have used the TF-IDF vectorizer, calculating the dot product will directly give us the cosine similarity score. Therefore, we will use sklearn's linear_kernel() instead of cosine_similarities() since it is faster.

Surprise Library Benchmarks
-------------
Here are the average RMSE, MAE and total execution time of various algorithms (with their default parameters) on a 5-fold cross-validation procedure. The datasets are the Movielens 100k and 1M datasets. The folds are the same for all the algorithms. All experiments are run on a notebook with Intel Core i5 7th gen (2.5 GHz) and 8Go RAM. The code for generating these tables can be found in the benchmark example.

![image](https://user-images.githubusercontent.com/37211139/186609049-dd934888-610e-47b4-8fdf-c0d552895b10.png)

Conclusion
-------------
![image](https://user-images.githubusercontent.com/37211139/186606700-216fd25c-f008-4369-9d27-f785ec49a515.png)

