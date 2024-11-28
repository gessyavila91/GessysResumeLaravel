# Setup Guide

This document provides instructions to set up the development environment for the application.

## Prerequisites

Before setting up the application, ensure you have the following prerequisites installed:

- **PHP**: Version 8.2 or higher
- **Composer**: Dependency management for PHP
- **Laravel**: PHP framework (installed via Composer)
- **Node.js**: Version 12 or higher (for front-end dependencies)
- **NPM or Yarn**: Package manager for Node.js
- **MySQL**: Database management system
- **Git**: Version control system
- **Docker**: Containerization platform (optional, but recommended for consistent environments)

## Installation Steps

### 1. Clone the Repository

First, clone the project repository to your local machine using Git:

```bash
git clone https://github.com/your-username/your-repository.git
cd your-repository
```
## 2. Install PHP Dependencies

Use Composer to install the PHP dependencies required by the application:

```
composer install
```

## 3. Install Node.js Dependencies

Use NPM or Yarn to install the front-end dependencies:

```
npm install
# or
yarn install
```

## 4. Set Up Environment Variables

Create a copy of the `.env.example` file and name it `.env`. Then, configure the environment variables according to your setup:

```
cp .env.example .env
```

Edit the `.env` file to set your database credentials and other configurations:

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_database_name
DB_USERNAME=your_database_username
DB_PASSWORD=your_database_password
```

## 5. Generate Application Key

Generate a unique application key, which is used for encryption and other purposes:

```
php artisan key:generate
```

## 6. Run Database Migrations

Run the database migrations to create the necessary tables:

```
php artisan migrate
```

## 7. Seed the Database

(Optional) Seed the database with initial data:

```
php artisan db:seed
```

## 8. Compile Assets

Compile the front-end assets (CSS, JavaScript, etc.):

```
npm run dev
# or
yarn dev
```

For production, you can use the production build command:

```
npm run prod
# or
yarn prod
```

## 9. Start the Development Server

Start the Laravel development server:

```
php artisan serve
```

By default, the application will be accessible at `http://127.0.0.1:8000`. You can also use tools like XAMPP, WAMP, or Laravel Valet for local development.

## Docker Setup (Optional)

If you prefer to use Docker, follow these steps:

### 1. Install Docker

Ensure you have Docker installed on your machine. You can download it from here.

### 2. Set Up Docker Containers

Use the provided `docker-compose.yml` file to set up the necessary containers:

```
docker-compose up -d
```

### 3. Run Database Migrations

Enter the application container and run the migrations:

```
docker-compose exec app php artisan migrate
```

## Additional Tips

- **IDE/Editor**: Use an IDE or code editor that supports PHP and JavaScript. Popular choices include Visual Studio Code, PHPStorm, and Sublime Text.

- **Debugging**: Use Laravel's built-in debugging tools like Laravel Debugbar and Xdebug for PHP.


## Dependencies

### Composer Dependencies

```json
"require": {
    "php": "^8.2",
    "laravel/framework": "^11.31",
    "laravel/tinker": "^2.9"
},
"require-dev": {
    "fakerphp/faker": "^1.23",
    "laravel/pail": "^1.1",
    "laravel/pint": "^1.13",
    "laravel/sail": "^1.26",
    "mockery/mockery": "^1.6",
    "nunomaduro/collision": "^8.1",
    "phpunit/phpunit": "^11.0.1"
}
```

### NPM/Yarn Dependencies

```json
"devDependencies": {
    "autoprefixer": "^10.4.20",
    "axios": "^1.7.4",
    "concurrently": "^9.0.1",
    "laravel-vite-plugin": "^1.0",
    "postcss": "^8.4.47",
    "tailwindcss": "^3.4.13",
    "vite": "^5.0"
}
```
