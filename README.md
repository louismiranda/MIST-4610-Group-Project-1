# Mist 4610 Group Project 1
## GROUP 1: Spotify Database

## Team Name: 
4610Fa24Group1 

## Team Members:

1. Louis Miranda [@louismiranda](https://github.com/louismiranda)
2. Bond Surber [@](https://www.github.com/apm83682)
3. Sidd Kawatra [@](https://www.github.com/RileyDoggett)

## Problem Description:

The task at hand is to model and build a relational database for the digital music streaming platform: Spotify. Spotify offers a few subscription plans for its users, millions of songs from different artists, and curated playlists made by either users or Spotify-themselves; therefore, the main entities in the model are SubscriptionPlan, User, Playlist, Song, Artist, and Advertisement. We are interested in accurately modeling these relationships, generating sample data, and populating the entities and their attributes with this sample data. Furthermore, we are interested in performing functioning queries on this data so that they may provide us with valuable business insight into both users and artists who utilize the platform, and the playlists and ads that Spotify operates. 

## Data Model

Explanation of data model: 

Our model is based on the structure of Spotify. The 'SubscriptionPlan' entity is representative of the select number of premium plans (Individual Premium, Family Premium, Student Premium, or Free) that Spotify offers for its users; this table tracks the type of subscription plan and their respective prices. Within each subscription plan, there are many users, and this is represented by the one-to-many relationship we have placed between the 'SubscriptionPlan' and 'User' entities. 

The 'User' entity keeps track of a Spotify user's username, age, country, and more. This entity branches off into 2 relationships: a one-to-many relationship with the 'Playlist' entity and a many-to-many relationship with the 'Song' entity (explained further down below). The one-to-many relationship with 'Playlist' showcases how Spotify users can have many playlists.  
The 'Playlist' entity keeps track of a playlist's name and creation date, and whether it was created by a user or Spotify-themselves. Each playlist on Spotify can have many songs, and each song can be on several playlists, which is represented through the many-to-many relationship we placed between the 'Playlist' and 'Song' entities (explained further down below).

The 'Song' entity can be thought of as the core of our data model because it includes 4 many-to-many relationships between the 'User', 'Playlist', 'Artist', and 'Advertisement' entities. 

In Spotify, users can interact with many songs through several means, such as liking or sharing a song, and each song can have many of these interactions with different users. As previously mentioned, this is represented through the many-to-many relationship that 'User' has with 'Song', which results in an associative entity called 'UserSongInteraction' that tracks whether users have liked or shared a song and the total number of times they've played a song.

Also previously mentioned, there is a many-to-many relationship between the 'Song' and 'Playlist' entities because many songs can be on different playlists, and each playlist can have many songs. We created an associative called 'PlaylistComposition' for the sole purpose of identifying which songs exists in each playlist, and which playlists have certain songs.

Similar to how users can have many playlists, Artists on Spotify can have several songs on the platform, resulting in a one-to-many relationship between the 'Artist' and 'Song' entities. This 'Artist' entity tracks the name of the artist, their monthly listeners (which is just a stored value, not calculated), and their country. Additionally, artists can collaborate on many songs, and songs can have many collaborations, so we created an associative entity called 'Collaboration' to keep track of the roles of each artist (i.e., producer, feature, etc.) who have collaborated on a song.

Lastly, Spotify allocates advertisements on each song, specifically for those who are free users, so we created an 'Advertisement' entity to keep track of the name of companies who have ads on the platform, as well as their advertising budget and how much they are paying everytime a Spotify user clicks on one of their ads. There is a many-to-many relationship between the 'Advertisement' and 'Song' entities because advertisements can appear on many songs, and songs can have different ads. As a result, we created an associative entity called 'AdvertisementDetails' to keep track of the type of ad, the ad's status, and the total number of times users have clicked on it.  


## Data Dictionary:
<img width="515" alt="Screenshot 2024-10-17 at 7 32 52 PM" src="https://github.com/user-attachments/assets/b8bec433-e6f0-47b3-89c3-84eb4de5ee4f">

<img width="518" alt="Screenshot 2024-10-17 at 7 33 59 PM" src="https://github.com/user-attachments/assets/f7c9852c-fb97-4334-820e-151965a142f9">

<img width="516" alt="Screenshot 2024-10-17 at 7 37 20 PM" src="https://github.com/user-attachments/assets/1cd1bb55-790e-46db-a60c-d6f85b794c7a">

<img width="517" alt="Screenshot 2024-10-17 at 7 41 54 PM" src="https://github.com/user-attachments/assets/62ea0a3a-3901-4be3-9875-d4942002078b">

<img width="515" alt="Screenshot 2024-10-17 at 7 46 53 PM" src="https://github.com/user-attachments/assets/b6de7415-bffd-45f2-acac-3eb42b89981f">

<img width="513" alt="Screenshot 2024-10-17 at 7 51 34 PM" src="https://github.com/user-attachments/assets/ce1e339b-64d7-4ade-8a84-bd369f48c2a6">

<img width="517" alt="Screenshot 2024-10-17 at 7 55 29 PM" src="https://github.com/user-attachments/assets/abf6a113-5c79-47ca-861b-a6a146e5435e">

<img width="511" alt="Screenshot 2024-10-17 at 7 57 56 PM" src="https://github.com/user-attachments/assets/ede21243-20c6-4a3a-ab67-c361454b4e26">

<img width="515" alt="Screenshot 2024-10-17 at 8 02 22 PM" src="https://github.com/user-attachments/assets/045b6c76-b945-464a-b677-d98ae7200b16">

<img width="514" alt="Screenshot 2024-10-17 at 8 08 20 PM" src="https://github.com/user-attachments/assets/1111c87b-552b-4468-99c3-b9794b3e7f39">

## Queries:

1. Query 1 lists the name of the most played song on Spotify and its total play count.

<img width="1096" alt="Screenshot 2024-10-17 at 8 22 20 PM" src="https://github.com/user-attachments/assets/8fa3c527-ca44-4ce5-a90e-1d54df91d123">

Query 1 allows allows managers to see which song is the most popular of all time. These songs tend to garner a broad audience of Spotify users and identifies the most popular streaming artist. Therefore, this query allows managers to leverage this information to determine the best song to highlight for future promotional campaigns, advertisements, collaborations, or brand deals


2. Query 2 lists the users who have played the song "Shape of You", their total play count of the song, and their percentage of play count from the overall total.

<img width="1097" alt="Screenshot 2024-10-17 at 8 23 27 PM" src="https://github.com/user-attachments/assets/0e45a612-f942-4277-ab6e-9699ab920f6d">

Query 2 allows managers to pinpoint users who have played "Shape of You", or any song in general, and compare their engagement with other users through their play count and percentage; the result is ordered in ascending order of their play count and respective percentages. This makes it easier to spot users who don't like a specific song as much as other users, who may be super fans, which signals to managers to remove the song from their curated playlists or from future recommendations, and vice versa. 










## Database information:

Name of the database: ns_4610Fa24Group1

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL TP_Q1();
