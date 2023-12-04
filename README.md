# EDA: Have music listening habits changed over the last 6 years? 

![Photo from above of someone listening to music on their hearphones](https://github.com/catisf/Project-1-Group-2/blob/main/readme_images/pexels-kaboompics-com-6399.jpg)

## Project 1 of UoB Data Bootcamp - Group 2

## Content:
1. [Project aim](https://github.com/catisf/Project-1-Group-2/tree/main#1-project-aim)
2. [Data collection and preparation](https://github.com/catisf/Project-1-Group-2/tree/main#2-data-collection-and-preparation)
3. [Definitions](https://github.com/catisf/Project-1-Group-2/tree/main#3-definitions)
4. [Main conclusions](https://github.com/catisf/Project-1-Group-2/tree/main#4-main-conclusions)
5. [Set up and running the code](https://github.com/catisf/Project-1-Group-2/tree/main#5-set-up-and-running-the-code)
6. [Repository structure](https://github.com/catisf/Project-1-Group-2/tree/main#6-repository-structure)
7. [Source code](https://github.com/catisf/Project-1-Group-2/tree/main#7-source-code)
8. [Collaborators/Team](https://github.com/catisf/Project-1-Group-2/tree/main#8-collaboratorsteam)

## 1. Project aim:
In this project, we aimed to understand **whether music listening habits have changed** in the last 6 years. 

There are two main reasons that lead us to believe music listening habits might have changed:
  - the global COVID pandemic (2020-2021) is likely to have lead to changes in how people listen to music and what music they listen to;
  - several articles mention the effects that the rise of social network TikTok (from 2018 on) is having on the music industry (see, for instance [here](https://theconversation.com/love-it-or-hate-it-tiktok-is-changing-the-music-industry-171482)).

We thus hypothesise that **listening habits are likely to have changed**, and asked the following questions to investigate our hypothesis:
1. Have the music genres people listen to changed?
2. Have the artists people listen to changed?
3. Is the duration of the most popular songs decreasing?
4. How have other track features changed?


## 2. Data collection and preparation
Every year, Spotify releases a playlist with the top 100 hit songs for that year. 

![Screenshot of Top hits 2017 playlist by Spotify](https://github.com/catisf/Project-1-Group-2/blob/main/readme_images/playlist.png)

In order to answer our research questions, we first selected 6 playlists, one for each of the last 6 years. We chose playlists spanning from 2017 to 2022, in order to capture both, any changes preceding the rise of TikTok and the COVID pandemic, as well as any long lasting changes in music listening habits post-COVID. 

The playlists for each year are the following:
- 2017: https://open.spotify.com/playlist/37i9dQZF1DWTE7dVUebpUW
- 2018: https://open.spotify.com/playlist/37i9dQZF1DXe2bobNYDtW8
- 2019: https://open.spotify.com/playlist/37i9dQZF1DWVRSukIED0e9
- 2020: https://open.spotify.com/playlist/2fmTTbBkXi8pewbUvG3CeZ
- 2021: https://open.spotify.com/playlist/5GhQiRkGuqzpWZSE7OU4Se
- 2022: https://open.spotify.com/playlist/56r5qRUv3jSxADdmBkhcz7

Once the playlists were selected, we used the [Spotipy API](https://spotipy.readthedocs.io/en/2.22.1/) - "a lightweight Python library for the Spotify Web API" - to request the following information about each track on the playlist:
- track ID
- track name 
- track popularity
- track features
- artist id
- artist name
- artist genre

You can find each of these features' definition in the [next section](https://github.com/catisf/Project-1-Group-2/tree/main#3-definitions). 

The information obtained from Spotipy was then combined into a single dataframe. The dataframe was carefully inspected for any missing data or duplicates, before being saved as a [.csv file](https://github.com/catisf/Project-1-Group-2/tree/main/output_data). Duplicated songs that were on playlists for different years were kept, as the same song might be in the top for more than one year and that information is relevant for our research questions.

## 3. Definitions
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


## 4. Main conclusions
As we hypothesized, **music habits seem to have changed in the past 6 years**. In our exploratory data analysis we found that:
1. Whilst pop and rap consistently occupy the first two positions at the top of the most listened-to genres, a lot of sub-genres of pop have risen around the period of COVID-19;
   
![Plot top 10 genres per year](https://github.com/catisf/Project-1-Group-2/blob/main/readme_images/top_genres_numsongs.png)

2. Only 5 artists had a song in the top 100 in every year, indicating people’s preferences change on a yearly base;
   
3. Songs are getting shorter in general. Song duration correlates strongly with the number of Tik-Tok users, so that the higher the number of Tik-Tok users, the smaller the duration of the songs
   
![Plot correlation duration vs tik tok users](https://github.com/catisf/Project-1-Group-2/blob/main/readme_images/duration_line_tiktok.png)

4. There has been a downward trend for features such as danceability and energy (songs score lower on these features), but the songs people listen to are becoming more positive (songs score higher on valence).  

### Limitations
It is important to bear in mind some limitations to our analyses. 
- Firstly, we only collected data for the most popular songs each year. These songs are likely to naturally share features, limiting our conclusions. In further analyses, it would be interesting to compare the features of top hit songs with significantly less popular songs. 
- Another limitation is that we only analysed data for the past 6 years. Although this allowed us to draw some conclusions around habits pre and post COVID, as well as how habits relate to TikTok usage, a lot of these trends might have been occurring for much longer. For instance, as [this article](https://www.billboard.com/pro/songs-getting-shorter-tiktok-streaming/) on Billboard suggests, the duration of top 100 hit songs has been changing since 2000. 
- Lastly, we chose to analyse the year a song was popular, not when it was released. Looking at songs' release dates might have shown a different picture altogether. 


## 5. Set up and running the code
### 1. Install dependencies
In order to run the files you will need to install the following packages:
- jupyter notebook `pip install notebook`
- matplotlib `pip install matplotlib`
- numpy `pip install numpy`
- pandas `pip install pandas`
- scipy `pip install scipy`
- spotipy `pip install spotipy`


### 2. Get Spotify credentials
Then you will need to get your Spotify credentials. On the [Spotify's Web API](https://developer.spotify.com/documentation/web-api) click on 'Getting started' and follow the instructions on the page to get your 'client_id' and 'client_secret'. 

> [!IMPORTANT]
> You need to have a Spotify account in order to request your credentials.


### 3. Run the code
Once all the packages have been installed:
1. Clone the repository
2. Open a text editor or VS code and copy your Spotify credentials (client_id and client_secret) onto a file named 'config.py', using the following syntax:

```
#  Add your API key
client_id = "ADD YOUR KEY HERE"
client_secret = "ADD YOUR KEY HERE"
```
   
3. Save the 'config.py' file in the 'jupyter_notebooks' folder in your local repository.
4. Run notebook 'spotipy_data_prep.ipynb' in the ['jupyter_notebooks' folder](https://github.com/catisf/Project-1-Group-2/tree/main/jupyter_notebooks). Alternatively, open the notebook 'spotipy_data_analyses.ipynb' directly, which downloads the data saved in a csv file in the ['output_data' folder](https://github.com/catisf/Project-1-Group-2/tree/main/output_data). Both notebooks include comments and annotations that will explain what the code is doing.
   

## 6. Repository structure
In this repository you can find:
- ['jupyter_notebooks' folder](https://github.com/catisf/Project-1-Group-2/tree/main/jupyter_notebooks) containing 2 jupyter notebooks. The notebook "spotipy_data_prep.ipynb" was used for data preparation. It contains the code used to set up permissions to access Spotipy, the list selection and the request for track features and information. The notebook "spotipy_data_analyses.ipynb" was used for all the data analyses. This notebook also includes markdown blocks that set out the aim of the project, explanation of the analyses and conclusions to be derived from them;
- ['output_data' folder](https://github.com/catisf/Project-1-Group-2/tree/main/output_data) containing a csv file ('spotipy_data.csv') with the data requested from the API, as well as all the plots resulting from the data analyses notebook.
- ['report' folder](https://github.com/catisf/Project-1-Group-2/tree/main/report) containing the slide deck for the presentation of the project


## 7. Source code
- Code in the data prep jupyter notebook is based on code shared by the instructor, as well as code from [Spotipy documentation](ttps://spotipy.readthedocs.io/en/2.22.1/) and from [here](https://towardsdatascience.com/extracting-song-data-from-the-spotify-api-using-python-b1e79388d50)
- Genre analysis: code to we unpack the artist genre column adapted from [here](https://www.learndatasci.com/solutions/python-pandas-dfexplode/)
- Code to plot subplots based on [matplotlib gallery](https://matplotlib.org/stable/gallery/subplots_axes_and_figures/subplots_demo.html)
- Code to plot subplots with 2 or more scales based on [matplotlib gallery](https://matplotlib.org/stable/gallery/subplots_axes_and_figures/two_scales.html)

## 8. Collaborators/Team
- [Catarina Ferreira](https://github.com/catisf)
- [Daniel Hughes](https://github.com/DanielHughes1580)
- [Bernard Tse](https://github.com/bernardtse)
- [Tafadzwa Fararira](https://github.com/BootcampCoderTF)
- [Kehlani Jaan Khan](https://github.com/kehlanijaan)
