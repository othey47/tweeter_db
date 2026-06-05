🌐 📱 Twitter-like Social Media System (ER + SQL Project)
🧠 Description

When talking about social media platforms, Twitter is one of the most popular systems for communication between users. It allows users to connect with thousands of people from different regions.

Each user creates an account and a profile containing:

Username
Account creation date
User bio (description)
Followers
Following
Tweets
Likes on tweets
🎯 Project Goal

You are required to simulate a simplified Twitter system using MySQL, including:

Users
Profiles
Tweets
Follow relationships
Likes system
📋 Requirements (SQL Project Tasks)
🧩 1. Database Design (ER Diagram First)

Before writing SQL:

Identify all entities (tables)
Define relationships between them
Draw an ER Diagram
Suggested entities:
Users
Profiles
Tweets
Follows (relationship table)
Likes (relationship table)
🔗 2. Relationships (Very Important)

You must correctly define:

One-to-One → User ↔ Profile
One-to-Many → User → Tweets
Many-to-Many → Users ↔ Users (Follow system)
Many-to-Many → Users ↔ Tweets (Likes system)

👉 Use FOREIGN KEYS

🏗️ 3. Create Database
CREATE DATABASE twitter_clone;
USE twitter_clone;
🧱 4. Create Tables

You must create tables for:

👤 Users
id (AUTO_INCREMENT)
username
email
password (encrypted)
created_at (auto timestamp)
🧾 Profiles
user_id (FK)
bio
profile_picture (optional)
🐦 Tweets
id (AUTO_INCREMENT)
user_id (FK)
content
created_at
🔗 Follows (User ↔ User)
follower_id
following_id
❤️ Likes
user_id
tweet_id
🔑 5. Auto-increment Requirement

Any ID column must be:

AUTO_INCREMENT
🔐 6. Password Encryption

When inserting a user:

Password must be stored using MD5 encryption

Example:

MD5('mypassword')
⏱️ 7. Auto Timestamp

When creating a user or tweet:

created_at must automatically use current time:
DEFAULT CURRENT_TIMESTAMP
⚙️ 8. Stored Procedure: createAccount
🎯 Purpose:

Create a user + profile at the same time.

Input:
username
email
password
bio
Behavior:
Insert into Users table
Get generated user ID
Insert into Profiles table
⚙️ 9. Stored Procedure: User_Follow
🎯 Purpose:

One user follows another user

Input:
follower username
following username
Behavior:
Find both user IDs
Insert into follows table
📊 10. Query Requirement

You must display:

👉 Number of tweets per user

Example output:

username	tweet_count
Ali	10
Sara	5
📦 11. Insert Data

You must:

Add sample users
Add tweets
Add follow relationships
Add likes
🧠 TIPS (VERY IMPORTANT)
You are NOT forced to use a fixed design → multiple solutions are allowed
ER diagram is required before SQL
Foreign keys must be used correctly
Follow normalization rules
🎯 Final Project Checklist

✔ ER Diagram created
✔ Database created
✔ Tables created
✔ Relationships (FK) added
✔ Sample data inserted
✔ Password encrypted with MD5
✔ AUTO_INCREMENT used
✔ Stored procedure createAccount
✔ Stored procedure User_Follow
✔ Query: count tweets per user
