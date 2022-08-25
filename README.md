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

![image](https://user-images.githubusercontent.com/37211139/186606700-216fd25c-f008-4369-9d27-f785ec49a515.png)

