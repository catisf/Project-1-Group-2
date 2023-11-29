# Have music listening habits changed over the last 6 years?
## Project 1 of UoB Data Bootcamp - Group 2

## Project aim:
In this project, we aimed to understand whether music listening habits have changed in the last 6 years. 

There are two main reasons that lead us to believe music listening habits have changed:
  - on the one hand, the global COVID pandemic (2020-2021) is likely to have lead to changes in how people listen to music and what music they listen to;
  - on the other hand, several articles mention the effects that the rise of social network TikTok (from 2018 on) might be having on the music industry [add references here]

We thus hypothesise that listening habits are likely to have changed, and asked X questions to try and answer our main question:
**1. Have the music genres people listen to changed?**
**2. Is the duration of the most popular songs decreasing?**
**3. How have track features changed?**
**4. Artist [change this to an actual question]**

## Data collection
In order to answer these questions, we first selected 6 playlists, with the top 100 hit songs for the past 6 years. We chose a year span between 2017 and 2022, in order to capture both any changes preceding the rise of TikTok and the COVID pandemic, and any long lasting changes post-COVID. 

The playlists for each year are the following:
- 2017: https://open.spotify.com/playlist/37i9dQZF1DWTE7dVUebpUW
- 2018: https://open.spotify.com/playlist/37i9dQZF1DXe2bobNYDtW8
- 2019: https://open.spotify.com/playlist/37i9dQZF1DWVRSukIED0e9
- 2020: https://open.spotify.com/playlist/2fmTTbBkXi8pewbUvG3CeZ
- 2021: https://open.spotify.com/playlist/5GhQiRkGuqzpWZSE7OU4Se
- 2022: https://open.spotify.com/playlist/56r5qRUv3jSxADdmBkhcz7

Once we defined these playlists, we used the [Spotipy API](https://spotipy.readthedocs.io/en/2.22.1/)  - "a lightweight Python library for the Spotify Web API" - to request the following information about each track on the playlist:
- track ID
- track name 
- track popularity
- track features
- artist id
- artist name
- artist genre

## Definitions

[Spotify's Web API](https://developer.spotify.com/documentation/web-api) defines the features we extracted for this project as follows:
### Track id
> Unique identifier for the track

### Track popularity
> The popularity of a track is a value between 0 and 100, with 100 being the most popular. The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are.

### Track features
#### Duration: 
> Track duration in ms

#### Danceability: 
> Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.

#### Energy:
> Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. 

#### Liveness: 
> Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live

#### Tempo: 
> The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.

#### Valence: 
> A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).

## About this repo
In this repo you can find:
- a folder with the [jupyter notebooks](https://github.com/catisf/Project-1-Group-2/tree/main/jupyter_notebooks) used for data preparation and data analyses. Data analyses notebooks include text that explains the analyses we are conduction and the conclusions from each step;
- a folder containing the data obtained from the API, as well as the plots resulting from the analyses notebook



## source code
some of the code to collect data from here: https://towardsdatascience.com/extracting-song-data-from-the-spotify-api-using-python-b1e79388d50
genre analysis: code to we unpack the artist genre column adapted from here: https://www.learndatasci.com/solutions/python-pandas-dfexplode/
ploting subplots: https://matplotlib.org/stable/gallery/subplots_axes_and_figures/subplots_demo.html
