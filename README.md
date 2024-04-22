## Movie-Plot-Similarities
This project applies natural language processing (NLP) techniques to analyze movie plot summaries from Wikipedia and IMDb. By merging and preprocessing text data from these two sources, the project seeks to uncover thematic and stylistic similarities across films, ultimately grouping them into clusters based on their narratives.

To run this project, you need to have Python installed on your system along with the following libraries:

> NumPy  <br>
> pandas  <br>
> NLTK  <br>
> scikit-learn  <br>
> Matplotlib  <br>
> seaborn  <br>

## Data Description
The dataset consists of movie plot summaries from Wikipedia and IMDb for a variety of films. Each entry contains the following columns:

> wiki_plot: Plot summary from Wikipedia.  <br>
> imdb_plot: Plot summary from IMDb.  <br>

These texts are often written in different styles and sometimes contain unique details pertinent to each source.

<p align="center">
  <img width="1000" height="400" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/movies_df.png">
</p>

## Data Preprocessing
The data preprocessing involves combining the wiki_plot and imdb_plot for each movie into a single column to enrich the text data. This combined plot summary undergoes further processing to prepare it for analysis:

**Tokenization**   <br>
Breaking text into sentences and words using NLTK's tokenization methods. This step includes filtering out tokens that are purely numeric or punctuation.

>**Stemming**   <br>
>Reducing words to their root form using the Snowball Stemmer. This helps in normalizing variations of the same word (e.g., 'fishing', 'fished', 'fisher' are all stemmed to 'fish').

>**Text Analysis**   <br>
>We apply TF-IDF vectorization to transform the processed text data into numeric form, enhancing the analysis by focusing on words that are most descriptive of each document while diminishing the importance of >frequently occurring words across documents.

>**Clustering**   <br>
>Using the K-means clustering algorithm, movies are grouped based on the similarity of their plot descriptions. This unsupervised learning technique identifies clusters that reflect underlying patterns and themes >across the films.

<p align="center">
  <img width="750" height="550" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/five%20clusters.png">
</p>

>**Visualization**   <br>
>Visual tools like dendrograms and bar plots are employed to illustrate the relationships between movies and the distribution across clusters, respectively.

Dendrograms help visualize the results of hierarchical clustering, which is an alternative to k-means clustering. Two pairs of movies at the same level of hierarchical clustering are expected to have similar strength of similarity between the corresponding pairs of movies.

<p align="center">
  <img width="1000" height="350" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/dendrogram.jpg">
</p>

The word clouds generated showcase the most common words to each cluster groups, the word similarities are the main factor influencing the cluster segregation.

<p align="center">
  <img width="600" height="400" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/wordcloud0.png">
</p>

<p align="center">
  <img width="600" height="400" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/worldcloud1.png">
</p>

<p align="center">
  <img width="600" height="400" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/worldcloud2.png">
</p>

<p align="center">
  <img width="600" height="400" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/worldcloud3.png">
</p>

<p align="center">
  <img width="600" height="400" src="https://github.com/gomeslelino/Movie-Plot-Similarities/blob/main/Pictures/worldcloud4.png">
</p>

## Model Deployment
A function was created called get_similar_movies( ), which returns a list of the ten movies out of the movies_df that are the most similar with the movie selected as a parameter and also showcases the ten most common words amongst the selected movie and the most similar movie. For example, when selection "Toy Story", the function returns:

> Top 10 common words between 'Toy Story' and 'Up':<br>
> hous: 0.6029<br>
> all: 0.3759<br>
> get: 0.2609<br>
> move: 0.2576<br>
> land: 0.2175<br>
> fli: 0.2072<br>
> run: 0.1815<br>
> new: 0.1596<br>
> save: 0.1304<br>

## Conclusion

This project showcases the application of natural language processing to analyze and visualize movie plot summaries, revealing thematic and narrative connections between films. By leveraging advanced NLP techniques and clustering, it offers insights into film genres and styles, for film enthusiasts, data scientists and linguists.
