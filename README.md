# musicsocianalysis
TITLE: Analysis of Society through Popular Music from the 2008 to 2023

*Link to the slide I used during NYU Data Science Club's Project EXPO presentation is at the bottom of README*


# Abstract: 

The purpose of this project is to engage in better understanding of our society using repeatedly arising themes in popular music throughout time periods. 

I believe that popular music is a great lens in viewing society at a given time. The musics we listen to are largely representative of our feelings, emotions, and attitude towards the outside world. 
Hence, the collective sum of tracks that were popular throughout the society we live in can be said to represent the feelings, emotions, and attitude towards the outside world of our society. 

For this project, I take the Bag of Words assumption to use, and used a Document Term Matrix (DTM) to arrange the lyrics. I used the *Spotify API* (1) and *Genius Lyrics API* (2) to gain access to Spotify's Top Hits playlist from 2008 to 2023 (1) and its lyrics (2). 
Then, I conducted a test of cosine similarity between the documents within the corpus (playlist) to prove the assumption that a single year's playlist is representative of a certain trend in society.

The effect of COVID was one of the most noticeable trends throughout the project. We became more reminiscent of the past, and became more self-acknowledging. Also, a trend in financial crises linked with the keyword 'money' was also conspicous. 

A shortcoming to this project is that it fails to focus on one singular trend, and should be addressed through a developed project that will succeed this project.

I expect this project to be extended to popular music scenes of other countries and/or regions, and prove to be an efficient way in understanding society with a nuanced objective in place.


# Process

<img width="600" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/8dd15f76-5062-4cd1-bfec-e2bd2da31786">

## Data Gathering 

For this project, I used Spotify API to obtain data from its *Top Hits Playlist* from 2008 to 2023, where I saved '''Track Titles''' , '''Track Artist''' , and '''Release Year''' into a python dictionary as the year as key. The years 2021 and 2023 did not have a publically available playlist, so I obtained them from Kaggle. url is inside the main jupyter notebook file. 

Now, all the tracks and artists are stored within a single python dictionary, for fast and efficient storage. 

The lyrics part was more tricky, but was the most fundamental part of this analysis project. I used the Genius API, since Spotify does not have a native lyrics database within its API. 

For each year (i.e. key in the original dictionary), I created empty folders in the main directory, with the year as the directory name. Then, I took the title and artist and input them into the Genius API search, and created .txt files within the sub directory created with the lyrics as content. 

Now, we have directorys from 2008 to 2023, containing lyrics from each playlists respectively. 

## Data Cleaning

For the Data Cleaning part of the process, I assumed two parts:
1. That each year (i.e. each corpus) will contain a certain trend.
2. Bag of Words (BoW), as in the semantics of the lyrics did not matter.
 

The lemmatization process was helped with the use of the nltk library and textblob library.

<img width="600" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/c161dfa0-6cde-42ad-9765-9771a8c201d4">

For assumption 1., I calculated the cosine similarity of each corpus, and given the innate heterogenity of musical lyrics, I concluded that it was a good enough consine similarity to continue with the given assumption.


# Some Analysis

Now that I have the data, I could continue with some analytical tasks, such as:

## Some Analysis on the Corpora

1. **Popular Places in Lyrics**
<img width="440" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/714b40a6-e54d-4e89-ad12-75b59f1f75d9">
<img width="320" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/1f06326f-9d4a-472d-9733-53a768a70143">

It is interesting to note the toponyms in song lyrics, such as in Jay-Z's 'Empire State of Mind', or 'Paris in the Rain'.
Cities appear quite often in popular lyrics. Especially New York City. 

We can see a trend in urban preference, in that metropolises such as NYC appear much more frequently than cities such as Cleveland. 


2. **Jobs in Lyrics**

<img width="424" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/1a2ee370-fc48-412d-aaf0-28e63aa6d455">

Some jobs are mentioned more than others in popular lyrics.
Mostly artistic occupations such as dancer, artist, designer are mentioned. We can't see traditionally respected occupations such as accountants or engineers. judge and lawyer are on the list, but should be viewed in pair with police, as related to judicial matters. 
We can notice a artistic admirance in occupations in lyrics, in that when people listen to music, they listen to what they think is 'cool.' And that they are frequently linked to artistic occupations. 


## Some Analysis on the Corpus

1. **Thinking of the Past**

<img width="625" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/44a67e5c-e139-4c60-9e3e-750d8ce47f0b">


Since COVID affected our lives, we started to realize how beautiful the normal life we had was, leading us to look back in the past
This trend is shown by the number of tracks that are not from the given year of analysis, but before it


2. **Relationship with the Economy**
<img width="594" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/18ca17c7-c6a3-47f9-a508-ebec41ac696f">

It's impossible to separate our society with the economy.
Then, with our assumption it is also impossible to separate it with popular music. 
spikes in the keyword 'money' has been related with economic crises


3. **Love as a Recurring Theme**
<img width="939" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/d8ff43be-8baa-4b27-b505-d9b4edebb59b">
<img width="379" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/7572083e-e780-4ea0-8a60-6aca86d74c56">

Love has always been a recurring theme in popular culture. 
Visibly, love has kept its place in the top list throughout the periods

4. **Recognizing "I" in Our Lives**
<img width="657" alt="image" src="https://github.com/belledcurve/musicsocianalysis/assets/92968898/9e614ed6-99c9-4062-bd9e-90a9d983bae7">

ratio = (# of 'I' - # of 'you') / # of 'you' 

have we become more self centered over the years? 
I believe it's not that but we started to focus more on our lives, as individuals, marked by the spike in 2023. 

# Further Studies

I have conducted some analytical researches into trends in popular music through this project. 

As a study, I acknowledge that it has some shortcomings, so I would like to add some aspects to my future project on a same subject

Technical aspect wise,
I would implement a better data structure to use a better sorting and search algorithm, such as the Boyer-Moore search algorithm.
Besides the use of a better search algorithm, a better data structure such as Tries would be necessary to store more text data efficiently. 

Outside of tehnical aspects,
I would expand the time frame, which was limited to the beginning of Spotify (around 2008)
To actually glance at generational data, I would need more ample data - reaching decades - and would need to find other data sources other than spotify. 

I would also probably conduct my next music society related project on the Korean society, as it is a society I am familiar with, and is also easy to analyze a vast difference in a very short time-frame, due to its fast-grown economy and society. 


Link to the presentation slide:
  https://docs.google.com/presentation/d/1wbdAsn6heG929vSMcy8LlES8US12zixzx9Wl7NcT5nA/edit?usp=sharing










