# Entity-Relationship Diagram (ERD) and Data Dictionary

This document contains both the ERD and the Data Dictionary for the application.

## Data Dictionary

TODO: add new entity "Achievements" for "user Goals"

| Entity Name          | Attributes                                             | Description                                                   |
|----------------------|--------------------------------------------------------|---------------------------------------------------------------|
| User                 | id, first_name, last_name, email, password, phone_number, address, city, state, country, postal_code, profile_image | Basic user information with contact details and profile image |
| Resume               | id, user_id, experience, education, skills, courses, languages_spoken | User's resume information                                      |
| Education            | id, resume_id, institution, degree, field_of_study, start_date, end_date, gpa, honors | Education details with GPA and honors                          |
| Experience           | id, resume_id, company, position, start_date, end_date, description, location, achievements | Work experience details with location and achievements         |
| Skill                | id, resume_id, name, type (SOFT/HARD), proficiency_level | Skills with type and proficiency level                         |
| Course               | id, resume_id, name, institution, completion_date, certificate_url | Courses and certifications with URL to certificate             |
| Language             | id, resume_id, name, proficiency                       | Languages spoken and proficiency levels                        |
| Hobby                | id, user_id, type, description, image                  | Information about user's hobbies with images                   |
| Project              | id, user_id, name, description, url, technologies_used, collaborators | User's projects (e.g., GitHub) with technologies used and collaborators |
| SocialMedia          | id, user_id, type, url, username, image                | User's social media accounts with username and profile image   |
| Book                 | id, user_id, title, author, genre, date_read, rating, review, image | User's favorite books with genre, rating, review, and cover image |
| Collectible          | id, user_id, type, description, acquired_date, value, image | Collectibles (e.g., TCG, physical video games) with acquisition date, value, and image |
| VideoGame            | id, user_id, title, platform, genre, date_played, hours_played, rating, review, image | Information about video games played by the user with hours played, rating, review, and cover image |
| Movie                | id, user_id, title, director, genre, date_watched, rating, review, image | Information about movies watched by the user with rating, review, and poster image |

## ERD Diagram

```mermaid
erDiagram
    User {
        int id PK
        string first_name
        string last_name
        string email
        string password
        string phone_number
        string address
        string city
        string state
        string country
        string postal_code
        string profile_image
    }
    Resume {
        int id PK
        int user_id FK
        string experience
        string education
        string skills
        string courses
        string languages_spoken
    }
    Education {
        int id PK
        int resume_id FK
        string institution
        string degree
        string field_of_study
        date start_date
        date end_date
        float gpa
        string honors
    }
    Experience {
        int id PK
        int resume_id FK
        string company
        string position
        date start_date
        date end_date
        string description
        string location
        string achievements
    }
    Skill {
        int id PK
        int resume_id FK
        string name
        string type
        string proficiency_level
    }
    Course {
        int id PK
        int resume_id FK
        string name
        string institution
        date completion_date
        string certificate_url
    }
    Language {
        int id PK
        int resume_id FK
        string name
        string proficiency
    }
    Hobby {
        int id PK
        int user_id FK
        string type
        string description
        string image
    }
    Project {
        int id PK
        int user_id FK
        string name
        string description
        string url
        string technologies_used
        string collaborators
    }
    SocialMedia {
        int id PK
        int user_id FK
        string type
        string url
        string username
        string image
    }
    Book {
        int id PK
        int user_id FK
        string title
        string author
        string genre
        date date_read
        float rating
        string review
        string image
    }
    Collectible {
        int id PK
        int user_id FK
        string type
        string description
        date acquired_date
        float value
        string image
    }
    VideoGame {
        int id PK
        int user_id FK
        string title
        string platform
        string genre
        date date_played
        int hours_played
        float rating
        string review
        string image
    }
    Movie {
        int id PK
        int user_id FK
        string title
        string director
        string genre
        date date_watched
        float rating
        string review
        string image
    }

    User ||--o{ Resume: has
    Resume ||--o{ Education: includes
    Resume ||--o{ Experience: includes
    Resume ||--o{ Skill: includes
    Resume ||--o{ Course: includes
    Resume ||--o{ Language: speaks
    User ||--o{ Hobby: enjoys
    User ||--o{ Project: works_on
    User ||--o{ SocialMedia: uses
    User ||--o{ Book: reads
    User ||--o{ Collectible: collects
    User ||--o{ VideoGame: plays
    User ||--o{ Movie: watches
