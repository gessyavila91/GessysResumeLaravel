# Data Dictionary

This document provides a detailed data dictionary for the application.

|Entity Name|Attributes|Description|
|---|---|---|
|User|id, name, email, password|Basic user information|
|Curriculum Vitae|id, user_id, experience, education, skills|User's CV information|
|Hobby|id, user_id, type, description|Information about user's hobbies|
|Project|id, user_id, name, description, url|User's projects (e.g., GitHub)|
|SocialMedia|id, user_id, type, url|User's social media accounts (Instagram, Twitter, etc.)|
|Video|id, user_id, platform, url|User's videos on platforms (e.g., YouTube)|
|Book|id, user_id, title, author|User's favorite books|
|Collectible|id, user_id, type, description|Collectibles (e.g., TCG, physical video games)|
