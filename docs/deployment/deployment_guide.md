# Deployment Guide

This document provides instructions for deploying the application.

## Prerequisites

Ensure you have the following prerequisites before starting the deployment:

- **Server**: A server with SSH access (e.g., VPS, cloud server like AWS, DigitalOcean)
- **Docker**: Installed on the server for containerization
- **Git**: Installed on the server for version control
- **Environment Variables**: Configured for the application

## Deployment Steps

### 1. Set Up the Server

1. **Update the Package List**: Ensure the server package list is up-to-date.
   ```bash
   sudo apt-get update
    ```
2. **Install Docker**: Follow the official Docker installation guide to install Docker on your server.

3. **Install Git**: Install Git for version control.

   bash

    ```
    sudo apt-get install git
    ```


### 2. Clone the Repository

Clone the project repository to the server:

bash

```
git clone https://github.com/your-username/your-repository.git
cd your-repository
```

### 3. Set Up Environment Variables

Create a copy of the `.env.example` file and name it `.env`. Configure the environment variables according to your setup:

bash

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

### 4. Set Up Docker Containers

Use the provided `docker-compose.yml` file to set up the necessary containers:

bash

```
docker-compose up -d
```

### 5. Run Database Migrations

Enter the application container and run the migrations:

bash

```
docker-compose exec app php artisan migrate
```

### 6. Seed the Database (Optional)

Seed the database with initial data (optional but recommended for testing):

bash

```
docker-compose exec app php artisan db:seed
```

### 7. Compile Assets

Compile the front-end assets (CSS, JavaScript, etc.):

bash

```
docker-compose exec app npm run prod
```

### 8. Set Up Nginx (Reverse Proxy)

1. **Install Nginx**:

   bash

    ```
    sudo apt-get install nginx
    ```

2. **Configure Nginx**: Create a new configuration file for your site:

   bash

    ```
    sudo nano /etc/nginx/sites-available/your-site
    ```

3. **Add the Nginx Configuration**:

   nginx

    ```
    server {
        listen 80;
        server_name your-domain.com;
    
        location / {
            proxy_pass http://127.0.0.1:8000;
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;
        }
    
        location ~ \.php$ {
            include snippets/fastcgi-php.conf;
            fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
        }
    
        location ~ /\.ht {
            deny all;
        }
    }
    ```

4. **Enable the Site**:

   bash

    ```
    sudo ln -s /etc/nginx/sites-available/your-site /etc/nginx/sites-enabled/
    ```

5. **Test Nginx Configuration**:

   bash

    ```
    sudo nginx -t
    ```

6. **Restart Nginx**:

   bash

    ```
    sudo systemctl restart nginx
    ```


### 9. Set Up SSL (Optional but Recommended)

Use Certbot to set up SSL for your domain:

bash

```
sudo apt-get install certbot python3-certbot-nginx
sudo certbot --nginx -d your-domain.com
```

Follow the instructions to obtain and install the SSL certificate.

### 10. Monitor and Maintain

Set up monitoring and maintenance tasks to ensure the application runs smoothly:

- **Monitoring**: Use tools like Prometheus and Grafana to monitor the application's performance.

- **Logging**: Implement logging with tools like ELK Stack (Elasticsearch, Logstash, Kibana).

- **Backups**: Schedule regular backups of the database and critical data.
