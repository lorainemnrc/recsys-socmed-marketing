![socmed_recsys_banner](https://github.com/lorainemnrc/recsys-socmed-marketing/assets/23328647/790faeb6-f057-47c0-909d-cee007431831)

<h1 style="color: #1048CB"><b>Overview</b></h1>

<p align="justify">&emsp;The effectiveness of influencer marketing is no longer up for debate. However, choosing who to partner with can be a significantly involved and relatively expensive process - not only do companies have to consider the influencers' reach, but more importantly, they have to consider the personality's values and how it align with theirs. A typical way for brands to reach influencers is through ad agencies. Agencies usually have a pool of influencers they can tap to partner with clients, and while this may greatly hasten the shortlisting process, agency fees are significant. High agency fees are why some brands choose to contact influencers directly instead. The obvious downside is the time and effort involved in scouting and communicating with potential partners.
</p>
<p align="justify">&emsp;Machine learning and information retrieval techniques help alleviate the tedious process of choosing who to partner with and can significantly improve the quality of the outcome. Using a brand's current social network and aggregating networks of the most influential personalities can provide a list of potential celebrity and influencer (micro and macro) partners - greatly streamlining the process and likely cutting on expenses.
 </p>

<h1 style="color: #1048CB"><b>Data Source</b></h1>

The necessary details of the scraping process are already detailed in the `main` notebook. However, a separate notebook `twitter_data_scraper.ipynb` file which lays out the whole process is also provided for more information.

<h2 style="color: #003b7f"><b>Influencers and their Tweets</b></h2>

**Influencers**

<p align="justify">
&emsp; We considered the users that an account follows to be its social network, and defined influencers as users who have at least 50,000 followers. In this work, 3 social networks were considered as the pool of potential partners that a brand can be matched with - Anne Curtis', Alden Richards, and the brand itself. Overall, 907 influencers were collected.
</p>
<p align="justify">
&emsp; Since Anne Curtis and Alden Richards were among the top 10 most followed Twitter users in the Philippines as of 2016, it was assumed that their social networks could represent a good sample set of influencers in the country. On the other hand, the brand's social circle was also added in the pool of potential partners assuming that they represent influencers that the brand already considers a good match.
</p>
<p align="justify">
&emsp; The https://api.twitter.com/2/users/:id/following endpoint was used to get the 3 social networks that make up the 907 pool of influencers. This query returns the profile of each whose contents are described briefly in Table 1.
</p>
<br>
<center style="font-size:12px;font-style:default;"><b>Table 1. Influencer Profile - Data Dictionary</b></center>

|Feature    | Data Type     | Description                                                                           |
|:--------------|:-------------|:--------------------------------------------------------------------------------------|
|id|string|unique identifier for each Twitter user
|description|string| Twitter bio description
|created_at|datetime|date of account creation
|username|string|Twitter user username
|protected|integer|indicates if Twitter account is protected or not
|name|string|real or formal name of Twitter user
|url|string|url link of Twitter account
|location|string|address of Twitter user
|followers_count|integer|indicates the number of followers the user has
|tweet_count|integer|indicates the number of tweets the user has posted
|listed_count|integer|indicates the number of lists the user is in
|included|integer|indicates if Twitter user is included in the consideration set
|rating|integer|indicates the rating of Twitter user


**Tweets**

<p align="justify">
&emsp;100 of the most recent tweets of each influencer as of 05 March 2023 were collected. The content of each influencer's tweets was assumed to reflect their ideals, values, and tone. This was used as the basis for evaluating whether an influencer is a good match with the brand. Overall, 88,135 tweets were gathered.
</p>
<p align="justify">
&emsp;The `https://api.twitter.com/2/users/:id/tweets` endpoint was used to get the tweets of each influencer. The contents of the scraped tweets are described briefly in Table 2.
</p>
<br>
<center style="font-size:12px;font-style:default;"><b>Table 2. Influencer Tweets - Data Dictionary</b></center>

|Feature    | Data Type     | Description                                                                           |
|:--------------|:-------------|:--------------------------------------------------------------------------------------|
|lang|string|indicates the language used for the tweet
|id|integer| unique identifier of the tweet
|created_at|datetime|date of creation of the tweet
|possibly_sensitive|integer|indicates if the topic of a tweet is sensitive or not
|author_id|integer|unique identifier for the author of the tweet
|conversation_id|integer|unique identifier for the specific tweet and its replies
|text|string|content of the tweet
|in_reply_to_user|integer|indicates if the tweet is a reply to another user id
|retweet count|integer|indicates the number of times the tweet was shared
|reply_count|integer|indicates the number of replies the tweet has recieved
|like_count|integer|indicates the number of likes the tweet has recieved
|quote_count|integer|indicates the number of times the tweet was quoted by another user
|impression_count|integer|indicates the number of impressions the tweet has garnered

***
<h2 style="color: #003b7f"><b>Brand</b></h2>

<p align="justify">
&emsp;This work considers Dove as the stakeholder who aims to find social media influencers that best match its brand image and values. Moving forward, "Dove" and the "Brand" may be used interchangeably.
</p>

<p align="justify">
&emsp;Dove's social network was obtained to determine which users are already "liked" by the brand. The tweets of Dove's social network were used as a basis for the brand's tone, values, and ideals that would be compared with that of the other potential partners in the matching process.
</p>

<h1 style="color: #1048CB"><b>Highlights</b></h1>

<p align="justify">
&emsp;Influencers can be categorized into three groups: (1) <strong><em>News and Entertainment outlets</em></strong>, (2) <strong><em>Celebrities</em></strong>, and (3) <strong><em>Social Media Micro- and Macro-influencers</em></strong>. Different brands and companies will have varying preferences on who to collaborate with, hinged on a few crucial factors: budget, intended reach or scope of influence, and whether or not the influencer's values match theirs. </p>

<p align="justify">
&emsp;Depending on the goal, our Content-Based Recommendation system, with an <strong><em>average relevance score of 0.90</em></strong>, can guide a brand in choosing the right influencer to partner with in their marketing campaigns. An efficient recommender system can afford brands several advantages. </p>

<p align="justify">
&emsp;An influencer whose values, audience, and interests align with the brand's target market ensures efforts are targeted, and the campaign's message reaches the right people. Influencer marketing can be more cost-effective than traditional advertising methods. Although high agency fees and commissions can be a limiting factor, it makes using a recommender system more cost-effective - allowing brands to identify influencers with a suitable audience size and engagement rate that fit their budget. </p>

<p align="justify">
&emsp; Based on the goals for using it, a business can save man-hours that could've been spent in scouring the social media sites for potential partners. With this system, the business is already given a short list of where to start that is more or less in line with its values as a business. </p>

<p align="justify">
&emsp; On the inverse, this system can also be used by influencers to look at potential business partners that they can reach out to. This may give them business opportunities that they would have not gotten. </p>
