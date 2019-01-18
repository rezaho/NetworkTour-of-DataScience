# Playlist Generation Based on Graph Theory

This project is part of "A Network Tour of Data Science" course.

The objective of this project is to generate a playlist that can bring the listener from his actual mood (e.g. angry or sad) to a mood he would like to be in (e.g. relaxed or happy).Through the light of networks, it is possible to examine how music tracks relate to each other. Can we build a playlist that links two very different tracks through a smooth transition? To answer this question, we will build a similarity graph between music tracks and choose a smooth path taking into account user's preference.

# Dataset
In total, the project used four datasets, namely:

1. User’s History (Million Songs Dataset): https://labrosa.ee.columbia.edu/millionsong/tasteprofile (download link)
2. Audio Features (from Spotify API): run code in [Collecting and Preproccessing Data](https://github.com/rezaho/NetworkTour-of-DataScience/blob/master/Collecting_and_Preproccessing_Data.ipynb)
3. MetaData (from Spotify API): run code in [Collecting Meta Data](https://github.com/rezaho/NetworkTour-of-DataScience/blob/master/Collecting_Meta_Data.ipynb)
4. Librosa Features (Computed with Librosa Library): run code in [Collecting and Preproccessing Data](https://github.com/rezaho/NetworkTour-of-DataScience/blob/master/Collecting_and_Preproccessing_Data.ipynb)

# Project
For detailed information about the project read our report.

Once all datasets are installed, the graph is generated:
[Creating Similarity Graph](https://github.com/rezaho/NetworkTour-of-DataScience/blob/master/Creating_Similarity_Networks.ipynb)

Finally, the following practical options are available to the use:
[Generating Playlist](https://github.com/rezaho/NetworkTour-of-DataScience/blob/master/Generating_Playlists.ipynb)

1. Seed/end song selection.

If the user wants the algorithm to define the seed(start) song or end song according to his/her mood selections,   he/she should assign to the variables end_song/seed_song the value returned by the function song_selection(Danceability,Energy,Valence) where the parameters represent the each mood dimension and should be between 0 and 1. 
If the user has a particular seed/end song that he wants to use, he/she can assign to the variables seed_song/end_song the corresponding node number of the desired songs (index of the adjacency matrix). 

2. Cutoff (playlist lenght)
If the user wants the playlist generated to have a specific lenght, he/she should adjust the variable "cutoff" in the network X method all_simple_paths. The playlist generated will have a maximum lenght of cutoff+1. Be aware that for comptational time reasons, cutoff should not be too much bigger (+3 max) than the shortest path lenght (otherwise to many paths are generated). 

3. Lambda factor: This factor can be adjusted depending on how much the user wants the songs in the playlist to take into account his taste. 


