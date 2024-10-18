# Mist 4610 Group Project 1
## GROUP 1: Spotify Database

## Team Name: 
4610Fa24Group1 

## Team Members:

1. Louis Miranda [@louismiranda](https://github.com/louismiranda)
2. Bond Surber [@bondsurber](https://www.github.com/bondsurber)
3. Sidd Kawatra [@siddKawatra](https://github.com/siddKawatra)

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

<img width="549" alt="Screenshot 2024-10-18 at 2 25 59 AM" src="https://github.com/user-attachments/assets/68ca2e09-79ed-4dbc-be86-2d8f779d8d58">

1. Query 1 lists the name of the most played song on Spotify and its total play count.

<img width="1096" alt="Screenshot 2024-10-17 at 8 22 20 PM" src="https://github.com/user-attachments/assets/8fa3c527-ca44-4ce5-a90e-1d54df91d123">

Query 1 allows allows managers to see which song is the most popular of all time. These songs tend to garner a broad audience of Spotify users and identifies the most popular streaming artist. Therefore, this query allows managers to leverage this information to determine the best song to highlight for future promotional campaigns, advertisements, collaborations, or brand deals


2. Query 2 lists the users who have played the song "Shape of You", their total play count of the song, and their percentage of play count from the overall total. The results are also ordered in ascending order of their play count and respective percentages.

<img width="1097" alt="Screenshot 2024-10-17 at 8 23 27 PM" src="https://github.com/user-attachments/assets/0e45a612-f942-4277-ab6e-9699ab920f6d">

Query 2 allows managers to pinpoint users who have played "Shape of You", or any song in general, and compare their engagement with other users through their play count and percentage. This makes it easier to spot users who don't like a specific song as much as other users, who may be super fans, which signals to managers to remove the song from their curated playlists or from future recommendations, and vice versa, allowing for a more tailored and customized user experience.

3. Query 3 lists the name of artists and their songs that are not currently in any playlists.

<img width="1096" alt="Screenshot 2024-10-17 at 8 43 36 PM" src="https://github.com/user-attachments/assets/1d0c024d-c238-4859-9e87-855d29166acd">

Query 3 allows managers to see which songs have not been added onto a playlist which indicates the artists and songs that may be under-promoted or overlooked. These song may have potential, but are not getting the attention that they deserve, so managers can introduce these songs to new playlists which will increase the diversity of users' playlist compositions while broadening the audience of underrepresented artists. 

4. Query 4 lists the total number of users and their average age for each subscription plan. 

<img width="1096" alt="Screenshot 2024-10-17 at 8 58 26 PM" src="https://github.com/user-attachments/assets/99ac9ddd-833e-4c70-af77-1461443a249f">

Query 4 allows managers understand the demographics behind each subscription plan which can help them to refine their pricing strategies, design targeted campaigns, or develop new features within a plan that tailors to a specific age group. For example, since the average user age for the "Student Premium" plan is 21 consisting of mostly people who are financially constricted, managers can leverage this by offering bundles or student discounts to capture most of the student market, increasing loyalty and boosting revenues, overall.

5. Query 5 lists all the countries that artists are from and the percentage of total user interactions associated with their songs.

<img width="1093" alt="Screenshot 2024-10-17 at 10 11 21 PM" src="https://github.com/user-attachments/assets/2834fe21-57c2-487a-8ca7-c5d3833c0f9f">

Query 5 allows managers to understand how user engagement is distributed across songs by artists from different countries and regions around the world. This gives managers a global perspective on the popularity of music in certain countries so that they can strategically form partnership with local artists from countries that show a high percentage of user interactions.

6. Query 6 lists the name of songs and their artists who have not recieved any likes and have not been shared.

<img width="1095" alt="Screenshot 2024-10-17 at 11 33 44 PM" src="https://github.com/user-attachments/assets/0761a8da-e5c0-4118-a306-0dad75438c16">

Query 6 allows managers to identify songs that users have played, but neither liked nor shared. Songs with no likes or shares are usually signs of underperformance and this is valuable feedback for both managers and artists since they can identify patterns or certain content that don't resonate well with users. Identifying underperforming songs is crucial for artists so that they know when to pivot into a new creative direction and make changes to their style. 

7. Query 7 lists the top 5 artists and their country in North America with the most song plays across all users. The results are also ordered in descending order of the aggregated play count.

<img width="1098" alt="Screenshot 2024-10-18 at 12 05 55 AM" src="https://github.com/user-attachments/assets/61fdbcfd-1525-4931-8e25-f20a1c7fc97f">

Query 7 allows managers to see the most popular artists in terms of song plays in North America. Since song plays often contribute to both artist revenue and platform income (via ads or subscriptions), promoting artists with high play counts can maximize revenue. Zoning in on the top 5 also helps managers keep track of artist rankings and set benchmarks for other artists looking to break into the top 5. 

8. Query 8 lists the name of songs and their genre that have "Pop" in the genre and a total play count greater or equal to 20

<img width="1096" alt="Screenshot 2024-10-18 at 12 43 38 AM" src="https://github.com/user-attachments/assets/44e68437-a95e-4998-a872-2ed2efce34c8">

Query 8 allows managers to identify successful songs specifically within the Pop genre and its other denominations. Not only can managers use this insight to make better Pop-centric playlists and song recommendations, but they can also identify emerging trends within specific genres, such as the growth of a new classification of Pop. For example, most of the songs outputted by the query were generic "Pop" songs, except for "Blinding Lights" which is a "Synth-pop" song, potentially showing that a new classification of Pop is gaining popularity. 

9. Query 9 lists the total amount that advertisement companies have paid Spotify for running their ads. This amount is calculated by multiplying the number of times users have clicked on the ad and the cost per click. The results are also ordered in descending order of the total cost. 

<img width="1097" alt="Screenshot 2024-10-18 at 1 30 24 AM" src="https://github.com/user-attachments/assets/c75e2757-2421-4e4f-a622-3b17c5fddb61">

Query 9 allows managers to see a clear picture of how much advertisement companies are paying Spotify for ads, allowing them to easily track the revenues from running ads. This information is also valuable for the advertisement companies because they can optimize their ad campaigns and assess whether their spending amounts align with their expected return on investment (ROI). 

10. Query 10 lists all the collaborations that the artist Dua Lipa has, including the song name and her role in the song. 

<img width="1094" alt="Screenshot 2024-10-18 at 2 13 06 AM" src="https://github.com/user-attachments/assets/60e8d20b-b7cf-4875-9abf-23f5267c606a">

Query 10 allows managers to see a comprehensive view of Dua Lipa's, or any artist's, collaborative work on Spotify. This insight is especially helpful for Dua Lipa's management team as they can identify trends or gaps in her collaborations, such as which roles she's already experienced in or which roles she has yet to try. In this case, Dua Lipa does not have a lot of collaborations so her team would suggest for her to form more connections with other artists to potentially collaborate and explore more roles.

## Database information:

Name of the database: ns_4610Fa24Group1

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL TP_Q1();
