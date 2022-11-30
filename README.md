# CA682I Data Management and Visualisation Project

Project guidelines presentation is recorded and made available on [zoom](https://dcu-ie.zoom.us/rec/play/4dGem9cv2a4KH4A4DBoB2ZtZiYouw2K7pCeX018WpJGH7euQmwbcVLcV6QJokzsTyBS9l7i27WSdcNfZ.o8piLTxZ3TNfD3Jb?startTime=1665075903000&_x_zm_rtaid=_EFvDPiHQL6wdRfcL-rkwQ.1667065330106.5bedcb362d2105f8fd4d3744869ba7d1&_x_zm_rhtaid=540).

Repository structure:
1. [code](code/) - tableau file that contains the visualisations
2. [resources](resource/) - a guide to selecting the right chart(s) for the narrative
3. [data](data/) - contains the datasets and python notebooks that were used to gather and clean data
   - [steamcharts](data/steamcharts/) - contains the jupyter notebooks and the relevant input and output data files associated with it.
   - [sentiment-analysis](data/sentiment-analysis/) - contains the jupyter notebook and the relevant input and output data files associated with it.
4. [inspiration](inspiration/) - images to get inspired from to tell a memorable narrative and compelling narrative 
5. [report](report/) - contains the report to be submitted 

## STEAM Charts
### Input
- unique_app_ids.csv - csv file exported from tableau that contains unique app/game ids in the steam_reviews.csv dataset (300+ games)

### Output
- steam_charts.csv - csv file generated by the processing phase that contains information shown in sample_output.json for each app/game

### Processing 
- data_gathering.ipynb - python code that queries the steam api and compiles the data into a dataset (csv file)
- data_cleaning.ipynb - python code that prepares and cleans the gathered dataset for visualisation

### Miscellaneous
- sample_output.json - example output returned by the steam api 

## Sentiment Analysis
### Input
- steam_reviews.csv - dataset obtained from [Kaggle](https://www.kaggle.com/datasets/najzeko/steam-reviews-2021)

### Output
- steam_review_cleaned_english.csv - csv file that contains the following columns that allows us to restart the kernel without having to clean the reviews everytime the kernel restarts  
  - app_id
  - app_name
  - review_id
  - language
  - review
  - **_review_cleaned_** - calculated by processing 
- [polarity](data/sentiment-analysis/polarity) values - there are 9M+ english reviews in the dataset. The polarity values had to be computed for a million reviews/rows at a time and written to a csv file, due to memory issues on my laptop
- sentiment_analysis_results_english.csv - csv file generated by the processing phase that contains all the necessary columns needed for visualisation

### Processing 
- steam_reviews_sentiment_analysis.ipynb - python code that runs sentiment analysis on the reviews and writes the results to a csv file for visualisation

## Datasets 
[Google Drive link](https://drive.google.com/drive/folders/1sP3HK-gHqvZ6jx_dlEvE-caYRJRl_bPQ?usp=share_link) to access the following.
- Final Datasets - final datasets used for visualisation in tableau
- Sentiment Analysis Data - datasets produced by the processing phase in Sentiment Analysis
- Steam Charts - google colab/jupter notebooks and data files that was needed to fetch player information (game statistics)  
