# Have music listening habits changed over the last 6 years?
## Project 1 of UoB Data Bootcamp - Group 2

## Aim of the project:
In this project, we aimed to understand whether music listening habits have changed in the last 6 years. 

There are two main reasons that lead us to believe music listening habits have changed:
  - on the one hand, the global COVID pandemic (2020-2021) is likely to have lead to changes in how people listen to music and what music they listen to;
  - on the other hand, several articles mention the effects that the rise of social network TikTok (from 2018 on) might be having on the music industry [add references here]

We thus hypothesise that listening habits are likely to have changed, and asked X questions to try and answer our main question:
1. Have the music genres people listen to changed?
2. Is the duration of the most popular songs decreasing?
3. How have track features changed?
4. Artist [change this to an actual question]

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

### Track id
Unique identifier for the track

### Track popularity
> The popularity of a track is a value between 0 and 100, with 100 being the most popular. The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are.

### Track features
#### Duration: 
Track duration in ms

#### Danceability: 
> Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.

#### Energy:
> Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. 

    




- did distribution of music genre changed pre and post covid
- did average music duration change pre and post covid
- do people listen to songs with different emotional valence pre and post covid
- do people listen to songs with different danceability pre and post covid
- do people listen to songs with different energy pre and post covid
- do people listen to songs with different loudeness pre and post covid
- are there artists who perform consistently pre and post covid


## source code
some of the code to collect data from here: https://towardsdatascience.com/extracting-song-data-from-the-spotify-api-using-python-b1e79388d50
genre analysis: code to we unpack the artist genre column adapted from here: https://www.learndatasci.com/solutions/python-pandas-dfexplode/
ploting subplots: https://matplotlib.org/stable/gallery/subplots_axes_and_figures/subplots_demo.html
