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


![Screen Shot 2023-03-30 at 9 42 10 PM](https://user-images.githubusercontent.com/128402101/229001455-ddc3361b-422f-483c-b4d8-01edc47e4afa.png)

## Data Dictionary:
![Screen Shot 2023-03-30 at 9 47 17 PM](https://user-images.githubusercontent.com/128402101/229002096-362cf55c-86b7-40e0-ae42-6120c5ab3d51.png)

![Screen Shot 2023-03-30 at 9 47 45 PM](https://user-images.githubusercontent.com/128402101/229002159-c7242e00-592e-4b10-9a09-1510a2728a4d.png)

![Screen Shot 2023-03-30 at 9 48 13 PM](https://user-images.githubusercontent.com/128402101/229002240-9817894f-9efd-4b15-af49-9712e8ec225b.png)

![Screen Shot 2023-03-30 at 9 55 12 PM](https://user-images.githubusercontent.com/128402101/229003109-3e9ec7ce-6368-4b85-95c8-facfa2fc1859.png)

![Screen Shot 2023-03-30 at 9 55 31 PM](https://user-images.githubusercontent.com/128402101/229003151-df7093e1-2245-4c2c-a2ed-7ae4b63c0f3f.png)

![Screen Shot 2023-03-30 at 9 56 18 PM](https://user-images.githubusercontent.com/128402101/229003272-e4f940d4-a2e6-428a-b009-719a7677b888.png)

![Screen Shot 2023-03-30 at 9 56 39 PM](https://user-images.githubusercontent.com/128402101/229003314-fe200a9c-db98-4447-b5d6-5f7d84e3f135.png)

![Screen Shot 2023-03-30 at 9 57 21 PM](https://user-images.githubusercontent.com/128402101/229003410-d264d5fa-52f4-412c-9663-7171571ad564.png)

![Screen Shot 2023-03-30 at 9 57 51 PM](https://user-images.githubusercontent.com/128402101/229003478-1b07581a-b8a2-4687-a4a7-9687c1cb2139.png)

![Screen Shot 2023-03-30 at 9 58 07 PM](https://user-images.githubusercontent.com/128402101/229003507-19f9582f-49a2-4cae-9d88-4eadb842ba66.png)

![Screen Shot 2023-03-30 at 9 58 29 PM](https://user-images.githubusercontent.com/128402101/229003554-6ae5e483-a161-4060-a113-ff7bbb5e4c1d.png)

![Screen Shot 2023-03-30 at 9 58 48 PM](https://user-images.githubusercontent.com/128402101/229003594-e640c190-4e87-4d4d-a81b-7f04085cbed8.png)

## Queries:

![Screen Shot 2023-03-31 at 6 37 36 PM](https://user-images.githubusercontent.com/128402101/229244775-f60ebfa8-49b5-4dc1-95f4-ae027192c111.png)

1. Query 1 lists the number of reservations at each dining establishment that were made for between 6 and 8pm as well as the name of each dining establishment these reservation were made for. The results are also ordered by number of reservations in descending order.

![Screen Shot 2023-03-31 at 5 50 12 PM](https://user-images.githubusercontent.com/128402101/229239154-7637136b-5ddd-400c-9335-f3e571507ed7.png)

Query 1 allows allows managers to see which establishments have received the most number of reservations during their busiest time (6-8pm) which is typically dinner time. These establishments likely need more support, resources, and personnel around dinner time. Therefore, this query allows managers to identify which establishments to allocate this extra help to. Listing the results in descending order of number of reservations makes it easier to see which establishment to prioritize.

2. Query 2 lists the number of dining reservations made by guests on each floor. The results are ordered in ascending order of floor number.

![Screen Shot 2023-03-31 at 5 50 39 PM](https://user-images.githubusercontent.com/128402101/229239237-725cac35-598a-49e5-9b5d-bfc96fb18714.png)

Query 2 allows managers to see whether there is a trend between what floor a guest stays on and how much they reserve tabes at the resort's dining establishments. If managers were to find that dining reservations decreased as the floor number increased, it would have possibly indicated that guests were not dining at dining establishments because they felt the distance of the dining establishment from their room was too far and inconvenient.

3. Query 3 lists the information for all the guests who have not made an activity reservation.

![Screen Shot 2023-03-31 at 5 52 01 PM](https://user-images.githubusercontent.com/128402101/229239403-19acc956-7345-406e-b7ba-a6eaf1c8db88.png)

Query 3 allows the resort to market toward specific customers and contact them (e.g. promotional emails/coupons) about must-try activities. This helps to maximize revenue and increase efficiency by specifically targeting those who are not engaging in activities, rather than wasting time and resources to advertise to those who are already aware of and partaking in these activities.

4. Query 4 lists the names and phone numbers of dining employees who work in the highest rated dining establishment.
 
![Screen Shot 2023-03-31 at 5 53 30 PM](https://user-images.githubusercontent.com/128402101/229239730-7f5416bd-0aff-4c4a-b64d-7f365f246a36.png)

A restaurant with a high star rating is a large source of revenue for the resort and management may want to know the names of the employees who work there and how to contact them to reward them for maintaining such a high achieving restaurant (e.g. via a bonus, raise, awards, recognition) or to know which employees to target for continuous training and supervision in order to keep service within the establishment in top shape.

5. Query 5 lists the guests’ names and the hotel they are checking into if their reservation is during the PM, their room is a single or suite, their check in dates are between 2023-04-01 and 2023-04-10, and their hotel rating is above a 4.

![Screen Shot 2023-03-31 at 5 54 41 PM](https://user-images.githubusercontent.com/128402101/229239947-e3c0ab47-c77c-474b-81c1-1b187548b89c.png)

Query 5 allows the resort to manage how busy their check in will be during the PM hours of early April in their better hotels where the check in rooms are singles or suites. This can help the resort determine how many employees need to be working the check in desks to check in single or suite reservations in the afternoon of these dates in these specific hotels.

6. Query 6 lists the names of guests who have over 10 activity reservations and the activities that they have those reservations in.

![Screen Shot 2023-03-31 at 5 55 37 PM](https://user-images.githubusercontent.com/128402101/229240045-10ca60c7-1cb2-49e2-a224-256c841e5fd8.png)

Query 6 allows the resort to determine what guests are contributing the most to each activity’s revenue. The resort may use this information to reward guests who spend the most on activities by offering special prizes and promotions, creating guest loyalty and creating an incentive to reserve even more.

7. Query 7 lists the the amount of dining reservations per guest and the average amount of guests these reservations have.

![Screen Shot 2023-03-31 at 5 56 06 PM](https://user-images.githubusercontent.com/128402101/229240108-152740f1-4c85-4a38-9194-c981cf33fc42.png)

Query 7 allows the resort to see how many guests they should plan to seat, how the tables should be set up, and can lead to the resort figuring out how much revenue should be expected for the average visit.

8. Query 8 lists the guestID, guest name, and the number of room reservations per guest.

![Screen Shot 2023-03-31 at 6 34 05 PM](https://user-images.githubusercontent.com/128402101/229244470-c29f68b3-f837-4a18-97bb-f86345b84431.png)

Query 8 allows the resort to identify their frequent customers and how many times they have stayed. This could lead to a card system down the line. If a guest reaches 5 or 10 visits, there could be a platinum card which would gift the user reservation priority, food discounts, and other perks.

9. Query 9 lists all the rooms along with their average room view rating if the rating is above a 4 star. Additionally, the query is sorted by the view rating and arranged in descending order.

![Screen Shot 2023-03-31 at 5 56 31 PM](https://user-images.githubusercontent.com/128402101/229240166-bb0bc849-08dd-4521-8608-7a85ff53ae46.png)

Query 9 allows the employees and customers to see which rooms have an average view rating of 4 or more. Rooms with extravagant views are huge attractions to customers and can be a deciding factor when picking which room to stay in. This will help employees find which rooms have the best views fast and efficiently when asked.

10. Query 10 lists the names and prices of all activities offered by the resort that have not yet been booked by any guests and that are less than or equal to $50. Additionally, the results of the query are ordered by price in ascending order.

![Screen Shot 2023-03-31 at 5 57 00 PM](https://user-images.githubusercontent.com/128402101/229240218-c01fb32b-5f71-4562-b014-b656bfe051bb.png)

Query 10 allows the employees and customers to see what activities have not been booked yet, and the prices for these activities. The price is sorted in ascending order to make it easier to find the most affordable activities which most people are looking for. Activities are a huge part of the resort experience and using this script will make it easy for employees to find which activities are available as well as the prices for these activities.

## Database information:

Name of the database: ns_21479_1

Additional information: Each query listed above is marked in the database using stored procedures which can be called using the following format: 
CALL TP_Q1();
