# CommonBank 
* **Project Title:** CommonBank
* **Database:** twitter_db

## Project Overview  
Due to shortage of information on official website I got some sample data and created a database twitter_db. This project will demonstrate engagement of the tweets on their twitter account by solving queries using the sample data and visually representing using Excel dashboard. The goal is to showcase skills in data analysis, data documentation, unstructured data and data visualization.

## Objectives
  1. Database Design: Create a database using 50 sample data. 
  2. CRUD operations: Extraction, combination and manipulation of data.
  3. Data Visualization and distribution: Representation of data through charts and graphs.

## **1. Database Designing**     
```sql
-- create table tweets
create table tweets (
    tweet_id bigint primary key,
    tweet_text text,
    created_at datetime,
    author_id bigint,
    retweets int,
    likes int,
    views int,
    sentiment varchar(15)
);

INSERT INTO tweets (tweet_id, tweet_text, created_at, author_id, retweets, likes, views, sentiment)
VALUES
(1001, 'Exciting news! We are launching a new savings feature for our customers. #BankingInnovation', '2024-03-15 08:30:00', 1, 120, 450, 5000, 'positive'),
(1002, 'We are experiencing technical issues with our mobile app. Our team is working to resolve this ASAP. Apologies for the inconvenience.', '2024-03-16 12:45:00', 1, 300, 150, 12000, 'negative'),
(1003, 'Happy to announce our partnership with fintech startups to bring better services to our customers. #FutureOfBanking', '2024-03-20 10:15:00', 1, 180, 520, 7200, 'positive'),
(1004, 'We value your feedback! Let us know how we can improve our services. #CustomerFirst', '2024-03-22 15:00:00', 1, 90, 230, 4000, 'neutral'),
(1005, 'Scam Alert 🚨 Be cautious of phishing emails pretending to be from CommBank. Always verify before clicking links. Stay safe!', '2024-03-25 17:30:00', 1, 500, 1200, 18000, 'negative'),
(1006, 'Introducing our new credit card with exclusive rewards! Apply now. #SmartSpending', '2024-04-01 09:00:00', 1, 250, 600, 7500, 'positive'),
(1007, 'Our branches will be closed on Good Friday. Plan your banking needs in advance. #BankingUpdate', '2024-04-02 14:00:00', 1, 130, 400, 6000, 'neutral'),
(1008, 'We have resolved the recent online banking issues. Thank you for your patience! #ServiceUpdate', '2024-04-05 11:20:00', 1, 180, 520, 8200, 'positive'),
(1009, 'We are aware of delays in international transactions and are working on a fix. Stay tuned.', '2024-04-08 16:45:00', 1, 320, 110, 10500, 'negative'),
(1010, 'New mobile app update available! Enjoy enhanced security and performance.', '2024-04-10 08:10:00', 1, 140, 500, 6200, 'positive'),
(1011, 'Big savings this season! Earn cashback on select purchases with our debit card. #SmartMoney', '2024-04-12 10:30:00', 1, 210, 550, 7000, 'positive'),
(1012, 'Reminder: Always set strong passwords for your online banking account. Security first!', '2024-04-14 14:00:00', 1, 180, 460, 6800, 'neutral'),
(1013, 'New branch opening in Sydney CBD! Visit us for personalized banking services. #LocalBanking', '2024-04-16 12:20:00', 1, 160, 480, 7200, 'positive'),
(1014, 'We are working to resolve the payment gateway issues. Apologies for any inconvenience caused.', '2024-04-18 17:40:00', 1, 350, 130, 11200, 'negative'),
(1015, 'Stay informed! Read our latest financial tips and tricks on our blog. #FinancialWellness', '2024-04-20 09:10:00', 1, 200, 510, 7400, 'positive'),
(1016, 'Thank you for your continued trust in CommBank. We appreciate our customers! #CustomerAppreciation', '2024-04-22 15:30:00', 1, 220, 540, 7600, 'positive'),
(1017, 'Due to scheduled maintenance, online banking will be unavailable from 2 AM - 4 AM AEST.', '2024-04-24 23:00:00', 1, 270, 350, 9000, 'neutral'),
(1018, 'Reminder: Never share your OTP or PIN with anyone. Stay safe from fraud!', '2024-04-26 11:15:00', 1, 500, 1200, 15000, 'negative'),
(1019, 'Planning your next trip? Enjoy no foreign transaction fees on our travel credit cards!', '2024-04-28 14:45:00', 1, 300, 700, 8800, 'positive'),
(1020, 'Excited to announce new home loan rates with flexible repayment options. #SmartLoans', '2024-04-30 16:20:00', 1, 240, 580, 7500, 'positive'),
(1021, 'We have increased ATM limits to provide better access to your funds! #ATMUpdates', '2024-05-02 10:00:00', 1, 180, 450, 6700, 'positive'),
(1022, 'We’re giving back! Get a 5% cashback on your first transaction with our new credit card. #BankingPerks', '2024-05-04 13:30:00', 1, 250, 550, 7600, 'positive'),
(1023, 'Important: Please be aware of a planned outage for maintenance on May 6. #ServiceAlert', '2024-05-06 16:00:00', 1, 300, 230, 8900, 'neutral'),
(1024, 'We’ve heard your feedback, and we’re making changes! Look out for improved app navigation soon. #AppUpdate', '2024-05-08 12:45:00', 1, 150, 420, 6300, 'positive'),
(1025, 'Quick reminder: Be cautious of unsolicited phone calls asking for your account details. #ScamAlert', '2024-05-10 09:25:00', 1, 400, 1100, 13500, 'negative'),
(1026, 'Your voice matters! Tell us about your CommBank experience through our survey and get a reward. #CustomerSurvey', '2024-05-12 14:10:00', 1, 220, 550, 7000, 'positive'),
(1027, 'Exciting news: New payment features are coming soon to help you pay smarter! #TechUpdate', '2024-05-14 10:00:00', 1, 270, 650, 8000, 'positive'),
(1028, 'Do you need financial advice? Book an appointment with one of our specialists today. #FinancialGuidance', '2024-05-16 11:40:00', 1, 150, 400, 5600, 'neutral'),
(1029, 'We’ve made a few changes to make your online banking more secure! Check out our new features. #SecurityUpdate', '2024-05-18 15:30:00', 1, 210, 500, 7100, 'positive'),
(1030, 'We are here for you. If you are facing difficulties due to recent events, please reach out to our support team. #CustomerSupport', '2024-05-20 13:15:00', 1, 300, 700, 9500, 'positive'),
(1031, 'We’re sorry! Due to a high volume of transactions, some users may experience delays. #ServiceUpdate', '2024-05-22 09:45:00', 1, 330, 120, 11000, 'negative'),
(1032, 'Take control of your financial future today! Explore our new savings plans. #SmartSaving', '2024-05-24 16:10:00', 1, 180, 480, 6800, 'positive'),
(1033, 'Introducing our new instant loan service – Fast approval, no paperwork! #QuickLoans', '2024-05-26 11:55:00', 1, 200, 500, 7500, 'positive'),
(1034, 'Stay safe online! Use two-factor authentication to secure your account. #CyberSecurity', '2024-05-28 10:30:00', 1, 350, 950, 12400, 'positive'),
(1035, 'Summer savings are here! Get exclusive discounts with CommBank’s new shopping partner. #ShoppingPerks', '2024-05-30 12:00:00', 1, 230, 600, 8300, 'positive'),
(1036, 'CommBank is committed to reducing our carbon footprint. Here’s what we’re doing to help. #SustainableBanking', '2024-06-01 09:40:00', 1, 270, 450, 6200, 'positive'),
(1037, 'Heads up: Expect delays for EFTPOS transactions nationwide due to system upgrades. #TechUpdate', '2024-06-03 17:10:00', 1, 280, 120, 10200, 'neutral'),
(1038, 'Win big with CommBank! Enter our competition for a chance to win a prize. #CommBankWin', '2024-06-05 14:20:00', 1, 220, 450, 6500, 'positive'),
(1039, 'Be aware of unexpected changes to your account? Get in touch with us today. #FraudAlert', '2024-06-07 13:00:00', 1, 350, 1400, 15000, 'negative'),
(1040, 'Don’t miss out! Get your hands on our exclusive banking offer for first-time customers. #WelcomeOffer', '2024-06-09 11:40:00', 1, 300, 700, 8800, 'positive'),
(1041, 'Now offering contactless payment options for your convenience. Pay faster with CommBank. #TechInnovation', '2024-06-11 16:25:00', 1, 210, 540, 7300, 'positive'),
(1042, 'Important reminder: Online banking will be undergoing scheduled maintenance on June 13. #MaintenanceAlert', '2024-06-13 09:15:00', 1, 190, 450, 6600, 'neutral'),
(1043, 'Enjoy stress-free banking with our new mobile features designed for your convenience. #AppUpdate', '2024-06-15 12:10:00', 1, 250, 560, 8000, 'positive'),
(1044, 'Need cash? Use any CommBank ATM nationwide with no fees for the next 30 days! #ATMFree', '2024-06-17 08:40:00', 1, 220, 480, 6500, 'positive'),
(1045, 'Due to an increase in traffic, our online services might experience slowdowns. Thank you for your patience.', '2024-06-19 10:00:00', 1, 300, 100, 10500, 'neutral'),
(1046, 'We’re going green! Our new sustainable banking initiative aims to reduce waste and energy consumption. #GreenBanking', '2024-06-21 12:45:00', 1, 280, 500, 7100, 'positive'),
(1047, 'Security alert: Be cautious of SMS phishing scams targeting bank users. #FraudAwareness', '2024-06-23 14:00:00', 1, 350, 1300, 14800, 'negative'),
(1048, 'Discover new ways to save with CommBank’s personalized financial planning tools. #SmartFinance', '2024-06-25 16:30:00', 1, 220, 510, 7000, 'positive'),
(1049, 'New features coming soon to improve your mobile banking experience. Stay tuned! #AppUpgrade', '2024-06-27 11:00:00', 1, 260, 560, 7500, 'positive'),
(1050, 'We’re here to help with financial advice. Book a session with a CommBank expert today! #FinancialPlanning', '2024-06-29 13:45:00', 1, 180, 450, 6400, 'neutral');

select * from tweets;
```
## **2. CRUD Operations**
```sql 
-- Examine CommBank’s most popular tweets.
alter table tweets 
add popularity int;
update tweets
set popularity = retweets + likes + views;

-- Everytime new tweets are added popularity will be calculated automatically
delimiter //

create trigger update_popularity 
before insert on tweets
for each row
begin
    set new.popularity = new.retweets + new.likes;
end;
//

delimiter ;

select * from tweets
order by popularity desc
limit 5;

# Query to Analyze Engagement by Time of Day
select 
    hour(created_at) as tweet_hour,
    count(*) as tweet_count,
    sum(popularity) as total_popularity
from tweets
group by tweet_hour
order by  total_popularity desc;

# Recurring words in high-engagement tweets
-- This sequence is used to extract individual words from a tweet.
with recursive numbers AS (
    select 1 as n
    union all
    select n + 1 
    from numbers 
    where n < 15
)
select 
    lower(substring_index(substring_index(tweet_text, ' ', n.n), ' ', -1)) as keyword, 
    count(*) as keyword_count
from 
    tweets 
join numbers n
on char_length(tweet_text) - char_length(replace(tweet_text, ' ', '')) >= n.n - 1
group by keyword
having keyword not in ('the', 'is', 'and', 'to', 'for', 'in', 'of', 'on', 'a', 'at')
order by keyword_count desc
limit 10;

-- Sentiment Distribution
select sentiment, COUNT(*) as count_sentiment
from tweets
group by sentiment;

-- Trending Sentiment Over Time
select 
    date(created_at) as tweet_date,
    sentiment,
    count(*) as sentiment_count
from tweets
group by tweet_date, sentiment
order by tweet_date;

-- Popularity Rank
alter table tweets add column popularity_d_rank int;
update tweets t
join
(select * ,
dense_rank() over (order by popularity desc) as ranking
from tweets) ranked_tweets
on t.tweet_id = ranked_tweets.tweet_id
set t.popularity_d_rank = ranked_tweets.ranking;

-- Most Popular Negative Tweets
select tweet_id, tweet_text, retweets, likes, popularity, popularity_d_rank
from tweets
where sentiment = 'Negative'
order by popularity desc
limit 5;

-- Most Popular Positive Tweets
select tweet_id, tweet_text, retweets, likes, popularity, popularity_d_rank
from tweets
where sentiment = 'Positive'
order by popularity desc
limit 5;

-- Most Popular Neutral Tweets
select tweet_id, tweet_text, retweets, likes, popularity, popularity_d_rank
from tweets
where sentiment = 'Neutral'
order by popularity desc
limit 5;

-- Tweets that Mention CommBank
select tweet_id, tweet_text, retweets, likes, sentiment, popularity_d_rank
from tweets
where tweet_text LIKE '%CommBank%';

```
## **3. Data Visualization and distribution**
# Summary of important metrics 
  ![1](https://github.com/Nidhi9608/-Commbank/blob/main/Summary%20of%20Key%20Metrics.png)

# Top 5 performing tweets 
  ![2](https://github.com/Nidhi9608/-Commbank/blob/main/Top%205%20popular%20tweets.png)


## Reports

## Conclusion



