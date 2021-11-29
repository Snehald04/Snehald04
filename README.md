
# import pandas library
import pandas as pd
 
# Get the data
column_names = ['user_id', 'item_id', 'rating', 'timestamp']
 
path = 'C:\Users\sgu\Downloads\file'
 
df = pd.read_csv(path, sep='\t', names=column_names)
 
# Check the head of the data
df.head()

# Check out all the movies and their respective IDs
movie_titles = pd.read_csv('[Movie_Id_Titles.csv](https://github.com/Snehald04/Snehald04/files/7616521/Movie_Id_Titles.csv)')
movie_titles.head()
data = pd.merge(df, movie_titles, on='item_id')
data.head()
# Calculate mean rating of all movies
data.groupby('title')['rating'].mean().sort_values(ascending=False).head()
