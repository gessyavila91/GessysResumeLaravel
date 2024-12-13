# API Documentation

This document provides details about the API endpoints available in the application.

## User Endpoints

### Get All Users
- **URL**: `/api/users`
- **Method**: `GET`
- **Description**: Retrieves a list of all users.
- **Response**:
```json
  [
    {
      "id": 1,
      "first_name": "John",
      "last_name": "Doe",
      "email": "john.doe@example.com",
      "profile_image": "http://example.com/images/john.jpg"
    },
    ...
  ]
```
### Get User by ID

- **URL**: `/api/users/{id}`

- **Method**: `GET`

- **Description**: Retrieves a single user by ID.

- **Response**:

  json

    ```
    {
      "id": 1,
      "first_name": "John",
      "last_name": "Doe",
      "email": "john.doe@example.com",
      "profile_image": "http://example.com/images/john.jpg"
    }
    ```


### Create User

- **URL**: `/api/users`

- **Method**: `POST`

- **Description**: Creates a new user.

- **Request**:

  json

    ```
    {
      "first_name": "John",
      "last_name": "Doe",
      "email": "john.doe@example.com",
      "password": "secret",
      "phone_number": "1234567890",
      "address": "123 Main St",
      "city": "Anytown",
      "state": "State",
      "country": "Country",
      "postal_code": "12345",
      "profile_image": "http://example.com/images/john.jpg"
    }
    ```

- **Response**:

  json

    ```
    {
      "id": 1,
      "first_name": "John",
      "last_name": "Doe",
      "email": "john.doe@example.com",
      "profile_image": "http://example.com/images/john.jpg"
    }
    ```


### Update User

- **URL**: `/api/users/{id}`

- **Method**: `PUT`

- **Description**: Updates an existing user.

- **Request**:

  json

    ```
    {
      "first_name": "John",
      "last_name": "Doe",
      "email": "john.doe@example.com",
      "phone_number": "1234567890",
      "address": "123 Main St",
      "city": "Anytown",
      "state": "State",
      "country": "Country",
      "postal_code": "12345",
      "profile_image": "http://example.com/images/john.jpg"
    }
    ```

- **Response**:

  json

    ```
    {
      "id": 1,
      "first_name": "John",
      "last_name": "Doe",
      "email": "john.doe@example.com",
      "profile_image": "http://example.com/images/john.jpg"
    }
    ```


### Delete User

- **URL**: `/api/users/{id}`

- **Method**: `DELETE`

- **Description**: Deletes a user.

- **Response**:

  json

    ```
    {
      "message": "User deleted successfully"
    }
    ```


## Resume Endpoints

### Get User's Resume

- **URL**: `/api/users/{id}/resume`

- **Method**: `GET`

- **Description**: Retrieves the resume of a specific user.

- **Response**:

  json

    ```
    {
      "id": 1,
      "user_id": 1,
      "experience": "...",
      "education": "...",
      "skills": "...",
      "courses": "...",
      "languages_spoken": "..."
    }
    ```


### Create/Update User's Resume

- **URL**: `/api/users/{id}/resume`

- **Method**: `POST`

- **Description**: Creates or updates the resume for a specific user.

- **Request**:

  json

    ```
    {
      "experience": "...",
      "education": "...",
      "skills": "...",
      "courses": "...",
      "languages_spoken": "..."
    }
    ```

- **Response**:

  json

    ```
    {
      "id": 1,
      "user_id": 1,
      "experience": "...",
      "education": "...",
      "skills": "...",
      "courses": "...",
      "languages_spoken": "..."
    }
    ```


## Hobby Endpoints

### Get User's Hobbies

- **URL**: `/api/users/{id}/hobbies`

- **Method**: `GET`

- **Description**: Retrieves the hobbies of a specific user.

- **Response**:

  json

    ```
    [
      {
        "id": 1,
        "user_id": 1,
        "type": "Reading",
        "description": "Reading books of various genres",
        "image": "http://example.com/images/hobbies/reading.jpg"
      },
      ...
    ]
    ```


### Create Hobby

- **URL**: `/api/users/{id}/hobbies`

- **Method**: `POST`

- **Description**: Creates a new hobby for a specific user.

- **Request**:

  json

    ```
    {
      "type": "Reading",
      "description": "Reading books of various genres",
      "image": "http://example.com/images/hobbies/reading.jpg"
    }
    ```

- **Response**:

  json

    ```
    {
      "id": 1,
      "user_id": 1,
      "type": "Reading",
      "description": "Reading books of various genres",
      "image": "http://example.com/images/hobbies/reading.jpg"
    }
    ```


## Project Endpoints

### Get User's Projects

- **URL**: `/api/users/{id}/projects`

- **Method**: `GET`

- **Description**: Retrieves the projects of a specific user.

- **Response**:

  json

    ```
    [
      {
        "id": 1,
        "user_id": 1,
        "name": "Project A",
        "description": "Description of Project A",
        "url": "http://example.com/projects/project-a",
        "technologies_used": "Laravel, Vue.js",
        "collaborators": "User B, User C"
      },
      ...
    ]
    ```


### Create Project

- **URL**: `/api/users/{id}/projects`

- **Method**: `POST`

- **Description**: Creates a new project for a specific user.

- **Request**:

  json

    ```
    {
      "name": "Project A",
      "description": "Description of Project A",
      "url": "http://example.com/projects/project-a",
      "technologies_used": "Laravel, Vue.js",
      "collaborators": "User B, User C"
    }
    ```

- **Response**:

  json

    ```
    {
      "id": 1,
      "user_id": 1,
      "name": "Project A",
      "description": "Description of Project A",
      "url": "http://example.com/projects/project-a",
      "technologies_used": "Laravel, Vue.js",
      "collaborators": "User B, User C"
    }
    ```


## Social Media Endpoints

### Get User's Social Media Accounts

- **URL**: `/api/users/{id}/socialmedia`

- **Method**: `GET`

- **Description**: Retrieves the social media accounts of a specific user.

- **Response**:

  json

    ```
    [
      {
        "id": 1,
        "user_id": 1,
        "type": "Instagram",
        "url": "http://instagram.com/johndoe",
        "username": "johndoe",
        "image": "http://example.com/images/socialmedia/instagram.jpg"
      },
      ...
    ]
    ```


### Create Social Media Account

- **URL**: `/api/users/{id}/socialmedia`

- **Method**: `POST`

- **Description**: Creates a new social media account for a specific user.

- **Request**:

  json

    ```
    {
      "type": "Instagram",
      "url": "http://instagram.com/johndoe",
      "username": "johndoe",
      "image": "http://example.com/images/socialmedia/instagram.jpg"
    }
    ```

- **Response**:

  json

    ```
    {
      "id": 1,
      "user_id": 1,
      "type": "Instagram",
      "url": "http://instagram.com/johndoe",
      "username": "johndoe",
      "image": "http://example.com/images/socialmedia/instagram.jpg"
    }
    ```

## Book Endpoints

### Get User's Books
- **URL**: `/api/users/{id}/books`
- **Method**: `GET`
- **Description**: Retrieves the books of a specific user.
- **Response**:
```json
  [
    {
      "id": 1,
      "user_id": 1,
      "title": "Book Title",
      "author": "Author Name",
      "genre": "Genre",
      "date_read": "2023-01-01",
      "rating": 5,
      "review": "This is a great book!",
      "image": "http://example.com/images/books/book.jpg"
    },
    ...
  ]
```

### Create Book

- **URL**: `/api/users/{id}/books`
    
- **Method**: `POST`
    
- **Description**: Creates a new book entry for a specific user.
    
- **Request**:
    
    json
    
    ```
    {
      "title": "Book Title",
      "author": "Author Name",
      "genre": "Genre",
      "date_read": "2023-01-01",
      "rating": 5,
      "review": "This is a great book!",
      "image": "http://example.com/images/books/book.jpg"
    }
    ```
    
- **Response**:
    
    json
    
    ```
    {
      "id": 1,
      "user_id": 1,
      "title": "Book Title",
      "author": "Author Name",
      "genre": "Genre",
      "date_read": "2023-01-01",
      "rating": 5,
      "review": "This is a great book!",
      "image": "http://example.com/images/books/book.jpg"
    }
    ```
    

## Collectible Endpoints

### Get User's Collectibles

- **URL**: `/api/users/{id}/collectibles`
    
- **Method**: `GET`
    
- **Description**: Retrieves the collectibles of a specific user.
    
- **Response**:
    
    json
    
    ```
    [
      {
        "id": 1,
        "user_id": 1,
        "type": "Trading Card",
        "description": "Rare trading card from 1990",
        "acquired_date": "2023-01-01",
        "value": 100.0,
        "image": "http://example.com/images/collectibles/card.jpg"
      },
      ...
    ]
    ```
    

### Create Collectible

- **URL**: `/api/users/{id}/collectibles`
    
- **Method**: `POST`
    
- **Description**: Creates a new collectible entry for a specific user.
    
- **Request**:
    
    json
    
    ```
    {
      "type": "Trading Card",
      "description": "Rare trading card from 1990",
      "acquired_date": "2023-01-01",
      "value": 100.0,
      "image": "http://example.com/images/collectibles/card.jpg"
    }
    ```
    
- **Response**:
    
    json
    
    ```
    {
      "id": 1,
      "user_id": 1,
      "type": "Trading Card",
      "description": "Rare trading card from 1990",
      "acquired_date": "2023-01-01",
      "value": 100.0,
      "image": "http://example.com/images/collectibles/card.jpg"
    }
    ```
    

## Video Game Endpoints

### Get User's Video Games

- **URL**: `/api/users/{id}/videogames`
    
- **Method**: `GET`
    
- **Description**: Retrieves the video games played by a specific user.
    
- **Response**:
    
    json
    
    ```
    [
      {
        "id": 1,
        "user_id": 1,
        "title": "Video Game Title",
        "platform": "Platform",
        "genre": "Genre",
        "date_played": "2023-01-01",
        "hours_played": 10,
        "rating": 5,
        "review": "Great game!",
        "image": "http://example.com/images/videogames/game.jpg"
      },
      ...
    ]
    ```
    

### Create Video Game

- **URL**: `/api/users/{id}/videogames`
    
- **Method**: `POST`
    
- **Description**: Creates a new video game entry for a specific user.
    
- **Request**:
    
    json
    
    ```
    {
      "title": "Video Game Title",
      "platform": "Platform",
      "genre": "Genre",
      "date_played": "2023-01-01",
      "hours_played": 10,
      "rating": 5,
      "review": "Great game!",
      "image": "http://example.com/images/videogames/game.jpg"
    }
    ```
    
- **Response**:
    
    json
    
    ```
    {
      "id": 1,
      "user_id": 1,
      "title": "Video Game Title",
      "platform": "Platform",
      "genre": "Genre",
      "date_played": "2023-01-01",
      "hours_played": 10,
      "rating": 5,
      "review": "Great game!",
      "image": "http://example.com/images/videogames/game.jpg"
    }
    ```
    

## Movie Endpoints

### Get User's Movies

- **URL**: `/api/users/{id}/movies`
    
- **Method**: `GET`
    
- **Description**: Retrieves the movies watched by a specific user.
    
- **Response**:
    
    json
    
    ```
    [
      {
        "id": 1,
        "user_id": 1,
        "title": "Movie Title",
        "director": "Director Name",
        "genre": "Genre",
        "date_watched": "2023-01-01",
        "rating": 5,
        "review": "Excellent movie!",
        "image": "http://example.com/images/movies/movie.jpg"
      },
      ...
    ]
    ```
    

### Create Movie

- **URL**: `/api/users/{id}/movies`
    
- **Method**: `POST`
    
- **Description**: Creates a new movie entry for a specific user.
    
- **Request**:
    
    json
    
    ```
    {
      "title": "Movie Title",
      "director": "Director Name",
      "genre": "Genre",
      "date_watched": "2023-01-01",
      "rating": 5,
      "review": "Excellent movie!",
      "image": "http://example.com/images/movies/movie.jpg"
    }
    ```
    
- **Response**:
    
    json
    
    ```
    {
      "id": 1,
      "user_id": 1,
      "title": "Movie Title",
      "director": "Director Name",
      "genre": "Genre",
      "date_watched": "2023-01-01",
      "rating": 5,
      "review": "Excellent movie!",
      "image": "http://example.com/images/movies/movie.jpg"
    }
    ```
    

