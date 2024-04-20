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
  <img width="1000" height="350" src="https://github.com/gomeslelino/Bridge-Classifier/blob/main/Pictures/BatchVisualization.png">
</p>

Methodology
Data Preprocessing
The data preprocessing involves combining the wiki_plot and imdb_plot for each movie into a single column to enrich the text data. This combined plot summary undergoes further processing to prepare it for analysis:

Tokenization
Breaking text into sentences and words using NLTK's tokenization methods. This step includes filtering out tokens that are purely numeric or punctuation.

Stemming
Reducing words to their root form using the Snowball Stemmer. This helps in normalizing variations of the same word (e.g., 'fishing', 'fished', 'fisher' are all stemmed to 'fish').

Text Analysis
We apply TF-IDF vectorization to transform the processed text data into numeric form, enhancing the analysis by focusing on words that are most descriptive of each document while diminishing the importance of frequently occurring words across documents.

Clustering
Using the K-means clustering algorithm, movies are grouped based on the similarity of their plot descriptions. This unsupervised learning technique identifies clusters that reflect underlying patterns and themes across the films.

Visualization
Visual tools like dendrograms and bar plots are employed to illustrate the relationships between movies and the distribution across clusters, respectively.
