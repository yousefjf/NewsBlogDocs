# Vedina News Project Documentation

## Table of Contents

- [Vedina News Project Documentation](#vedina-news-project-documentation)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Backend](#backend)
    - [Technology Stack](#technology-stack)
    - [Project Structure](#project-structure)
    - [API Documentation](#api-documentation)
    - [Just-In-Time Compilation in Node.js](#just-in-time-compilation-in-nodejs)
    - [Performance Benefits of Async Node.js](#performance-benefits-of-async-nodejs)
  - [Frontend](#frontend)
    - [Technology Stack](#technology-stack-1)
    - [Features](#features)
    - [Caching Strategy](#caching-strategy)
    - [Live Demo](#live-demo)
  - [Admin Panel](#admin-panel)
    - [Technology Stack](#technology-stack-2)
    - [Features](#features-1)
    - [Live Demo](#live-demo-1)
  - [Database](#database)
    - [Database Schema](#database-schema)
    - [SQL Scripts](#sql-scripts)
  - [Deployment](#deployment)
    - [Development Environment](#development-environment)
    - [Production Environment](#production-environment)
  - [Webserver](#webserver)
    - [Nginx Configuration](#nginx-configuration)
    - [Security and Performance](#security-and-performance)
  - [Conclusion](#conclusion)
  - [Future Enhancements](#future-enhancements)

---

## Introduction

Vedina News is a comprehensive news blogging platform that serves as a central hub for news consumption and administration. This documentation provides an in-depth overview of the project, including its architecture, technology stack, and deployment strategies.

---

## Backend

### Technology Stack

- **Programming Language:** JavaScript (Node.js)
- **Framework:** Express.js (Latest Version)
- **Database:** MySQL 8 LTS
- **API Documentation:** Swagger UI (Available at [https://api.news.vedina.ir/api-docs/](https://api.news.vedina.ir/api-docs/))

### Project Structure

The backend project is structured as follows:

```
app.js
config/
database/
models/
routes/
server.js
test/
validator/
auth/
controllers/
db.js
docs/
nginx.conf
public/
scrapper/
ssl/
utilities/
```

- **app.js:** The main application file that initializes the Express app.
- **config/:** Configuration files for the application.
- **database/:** Database connection and migration scripts.
- **models/:** Mongoose models for database interactions.
- **routes/:** API routes definition.
- **server.js:** Entry point of the application.
- **test/:** Test cases for the application.
- **validator/:** Custom validators for input data.
- **auth/:** Authentication-related functions.
- **controllers/:** Business logic for API endpoints.
- **db.js:** Database connection setup.
- **docs/:** Documentation files.
- **nginx.conf:** Nginx configuration for reverse proxy.
- **public/:** Public assets.
- **scrapper/:** News scraping utilities.
- **ssl/:** SSL certificates for HTTPS.
- **utilities/:** Helper functions and utilities.

### API Documentation

The API documentation is available via Swagger UI at [https://api.news.vedina.ir/api-docs/](https://api.news.vedina.ir/api-docs/). Below is a list of all backend resources:

- **Admin Logs**

  - `GET /admin-logs`: Get all admin logs.
  - `POST /admin-logs`: Create a new admin log.
  - `GET /admin-logs/{id}`: Get admin log by ID.
  - `DELETE /admin-logs/{id}`: Delete admin log by ID.

- **Categories**

  - `GET /categories`: Get all categories.
  - `POST /categories`: Create a new category.
  - `GET /categories/{id}`: Get category by ID.
  - `DELETE /categories/{id}`: Delete category by ID.
  - `PATCH /categories/{id}`: Update category by ID.

- **Comments**

  - `GET /comments`: Get all comments.
  - `POST /comments`: Create a new comment.
  - `GET /comments/news/{newsId}`: Get comments by news ID.
  - `GET /comments/{id}`: Get comment by ID.
  - `DELETE /comments/{id}`: Delete comment by ID.
  - `PATCH /comments/{id}`: Update comment by ID.
  - `GET /comments/{id}/replies`: Get replies to a comment.

- **Likes**

  - `POST /likes`: Create a like.
  - `GET /likes/news/{newsId}`: Get likes for a news.
  - `DELETE /likes/{id}`: Delete like by ID.

- **Media**

  - `POST /media`: Create media.
  - `GET /media/news/{newsId}`: Get media by news ID.
  - `GET /media/{id}`: Get media by ID.
  - `DELETE /media/{id}`: Delete media by ID.
  - `PATCH /media/{id}`: Update media by ID.

- **News**

  - `GET /news`: List all news.
  - `POST /news`: Create new news.
  - `GET /news/{id}`: Get news by ID.
  - `DELETE /news/{id}`: Delete news by ID.
  - `PATCH /news/{id}`: Update news by ID.

- **Tags**

  - `GET /tags`: Get all tags.
  - `POST /tags`: Create a new tag.
  - `GET /tags/{id}`: Get tag by ID.
  - `DELETE /tags/{id}`: Delete tag by ID.
  - `PATCH /tags/{id}`: Update tag by ID.

- **User Activity Logs**

  - `GET /user-activity/user/{userId}`: Get user activity logs.
  - `GET /user-activity/action/{actionType}`: Get logs by action type.

- **User Roles**

  - `GET /user-roles`: Get all user roles.
  - `POST /user-roles`: Create a new user role.
  - `GET /user-roles/{id}`: Get user role by ID.
  - `DELETE /user-roles/{id}`: Delete user role by ID.
  - `PATCH /user-roles/{id}`: Update user role by ID.

- **Users**
  - `GET /users`: List all users.
  - `POST /users`: Create a new user.
  - `GET /users/{id}`: Get user by ID.
  - `DELETE /users/{id}`: Delete user by ID.
  - `GET /users/stats`: Get user stats.
  - `GET /users/comments`: Get user comments.
  - `GET /users/favorites`: Get user favorites.
  - `PATCH /users/`: Update user by ID.
  - `PUT /users/password`: Change user password.
  - `POST /users/login`: User login.

### Just-In-Time Compilation in Node.js

Node.js uses V8, Google's open-source JavaScript engine, which employs Just-In-Time (JIT) compilation to improve performance. JIT compilation converts JavaScript code into machine code at runtime, allowing for optimizations that are not possible with traditional interpretation.

**Performance Benefits:**

- **Faster Execution:** JIT compilation allows for faster execution of JavaScript code by compiling it into optimized machine code.
- **On-Demand Compilation:** Only the code that is actually used is compiled, which can lead to better performance and reduced memory usage.
- **Dynamic Optimization:** V8 can optimize code based on runtime profiles, leading to better performance for frequently executed code paths.

### Performance Benefits of Async Node.js

Node.js is designed to handle asynchronous operations efficiently, which is crucial for building scalable web applications.

**Key Benefits:**

- **Non-Blocking I/O:** Node.js uses a non-blocking I/O model, which allows it to handle multiple requests concurrently without waiting for I/O operations to complete.
- **Event-Driven Architecture:** The event loop in Node.js efficiently manages asynchronous operations, leading to improved performance and scalability.
- **High Concurrency:** Node.js can handle a large number of concurrent connections, making it ideal for real-time applications and APIs.

---

## Frontend

### Technology Stack

- **Framework:** Vanilla JavaScript, HTML, CSS
- **UI Library:** Bootstrap
- **Custom Frameworks:** Private frameworks owned by Vedina Co.
- **Caching Strategy:** Advanced caching strategies for optimal performance

### Features

- **Progressive Web App (PWA):** Provides a seamless experience across devices.
- **Responsive Design:** Optimized for all screen sizes.
- **Advanced Caching:** Enhances performance and offline capabilities.
- **Custom Frameworks:** Built-in utilities for managing state and routing.

### Caching Strategy

The frontend employs an advanced caching strategy to ensure optimal performance:

- **Service Workers:** Leverage service workers for caching and offline support.
- **Cache Storage:** Utilizes the Cache API for storing and retrieving resources.
- **Stale-While-Revalidate:** Serves cached content while updating it in the background.

### Live Demo

- **URL:** [https://news.vedina.ir](https://news.vedina.ir)

---

## Admin Panel

### Technology Stack

- **Framework:** React 19
- **UI Library:** Custom components and themes
- **State Management:** Redux or Context API (as per implementation)

### Features

- **User Management:** CRUD operations for users.
- **Content Management:** Manage news, categories, tags, and media.
- **Analytics Dashboard:** View site statistics and user activity.
- **Logging:** Monitor admin activities and logs.

### Live Demo

- **URL:** [https://admin.news.vedina.ir](https://admin.news.vedina.ir)

---

## Database

### Database Schema

The database is designed using MySQL 8 LTS. Below is the SQL schema for the database:

```sql
CREATE TABLE admin_logs (
  log_id INT NOT NULL AUTO_INCREMENT,
  user_id INT NOT NULL,
  action_type VARCHAR(50) NOT NULL,
  description TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (log_id),
  FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE categories (
  category_id INT NOT NULL AUTO_INCREMENT,
  category_name VARCHAR(100) NOT NULL UNIQUE,
  description TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (category_id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE comments (
  comment_id INT NOT NULL AUTO_INCREMENT,
  user_id INT NOT NULL,
  news_id INT NOT NULL,
  parent_comment_id INT,
  comment_text TEXT NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (comment_id),
  FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE,
  FOREIGN KEY (news_id) REFERENCES news(news_id) ON DELETE CASCADE,
  FOREIGN KEY (parent_comment_id) REFERENCES comments(comment_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE likes (
  like_id INT NOT NULL AUTO_INCREMENT,
  user_id INT NOT NULL,
  news_id INT NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (like_id),
  FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE,
  FOREIGN KEY (news_id) REFERENCES news(news_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE media (
  media_id INT NOT NULL AUTO_INCREMENT,
  news_id INT NOT NULL,
  media_url VARCHAR(255) NOT NULL,
  media_type ENUM('image', 'video') NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (media_id),
  FOREIGN KEY (news_id) REFERENCES news(news_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE news (
  news_id INT NOT NULL AUTO_INCREMENT,
  title VARCHAR(255) NOT NULL,
  text TEXT NOT NULL,
  publication_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  publishing_admin INT NOT NULL,
  category_id INT,
  likes_count INT DEFAULT 0,
  comments_count INT DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (news_id),
  FOREIGN KEY (publishing_admin) REFERENCES users(user_id) ON DELETE CASCADE,
  FOREIGN KEY (category_id) REFERENCES categories(category_id) ON DELETE SET NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE news_tags (
  news_id INT NOT NULL,
  tag_id INT NOT NULL,
  PRIMARY KEY (news_id, tag_id),
  FOREIGN KEY (news_id) REFERENCES news(news_id) ON DELETE CASCADE,
  FOREIGN KEY (tag_id) REFERENCES tags(tag_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE password_recovery (
  recovery_id INT NOT NULL AUTO_INCREMENT,
  user_id INT NOT NULL,
  recovery_token VARCHAR(255) NOT NULL,
  expiration_time DATETIME NOT NULL,
  is_used TINYINT(1) DEFAULT 0,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (recovery_id),
  FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE tags (
  tag_id INT NOT NULL AUTO_INCREMENT,
  tag_name VARCHAR(100) NOT NULL UNIQUE,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (tag_id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE users (
  user_id INT NOT NULL AUTO_INCREMENT,
  username VARCHAR(50) NOT NULL UNIQUE,
  email VARCHAR(40) NOT NULL UNIQUE,
  phone VARCHAR(15) NOT NULL UNIQUE,
  password VARCHAR(255) NOT NULL,
  role_id INT NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  PRIMARY KEY (user_id),
  FOREIGN KEY (role_id) REFERENCES user_roles(role_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE user_activity_logs (
  log_id INT NOT NULL AUTO_INCREMENT,
  user_id INT NOT NULL,
  action_type VARCHAR(50) NOT NULL,
  target_id INT,
  target_type ENUM('news', 'comment', 'user', 'category', 'tag'),
  description TEXT,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (log_id),
  FOREIGN KEY (user_id) REFERENCES users(user_id) ON DELETE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;

CREATE TABLE user_roles (
  role_id INT NOT NULL AUTO_INCREMENT,
  role_name ENUM('master', 'admin', 'user', 'guest') NOT NULL UNIQUE,
  permissions JSON NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (role_id)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_general_ci;
```

### SQL Scripts

The above SQL scripts define the database schema for Vedina News. Each table represents a specific entity in the application, and the relationships between them are defined using foreign keys.

---

## Deployment

### Development Environment

For development, the application is containerized using Docker Compose. Below is the configuration:

```yaml
services:
  node:
    image: newsblog:dev
    build:
      context: .
      dockerfile: Dockerfile.dev
    container_name: node
    user: node
    working_dir: /usr/src/app
    volumes:
      - .:/usr/src/app
      - node_modules:/usr/src/app/node_modules
    environment:
      - NODE_ENV=development
      - CHOKIDAR_USEPOLLING=true
    command: npm run dev
    logging:
      driver: "json-file"
      options:
        max-size: "10m"
        max-file: "3"
    networks:
      - private
    depends_on:
      - mysql
      - redis

  mysql:
    image: mysql:8.4
    container_name: mysql
    environment:
      MYSQL_ROOT_PASSWORD: $password
      MYSQL_DATABASE: news_blog
      MYSQL_USER: news_blog
      MYSQL_PASSWORD: $password
    volumes:
      - mysql_data:/var/lib/mysql
    networks:
      - private

  redis:
    image: redis:latest
    container_name: redis
    volumes:
      - redis_data:/data
    networks:
      - private

  phpmyadmin:
    image: phpmyadmin:latest
    container_name: phpmyadmin
    environment:
      UPLOAD_LIMIT: 64M
      PMA_HOST: mysql
      PMA_PORT: 3306
    ports:
      - "8101:80"
    networks:
      - public
      - private
    depends_on:
      - mysql

  nginx:
    image: nginx:latest
    container_name: nginx
    volumes:
      - ../frontend/dist:/usr/share/nginx/html/news:ro
      - ../admin/dist:/usr/share/nginx/html/admin:ro
      - ./nginx.conf:/etc/nginx/conf.d/default.conf:ro
      - ./ssl/main:/etc/nginx/ssl/news:ro
      - ./ssl/admin:/etc/nginx/ssl/admin:ro
      - ./ssl/api:/etc/nginx/ssl/api:ro
    ports:
      - "8080:80"
      - "8443:443"
    networks:
      - public
      - private
    restart: unless-stopped
    depends_on:
      - node

networks:
  public:
    driver: bridge
  private:
    driver: bridge
    internal: false

volumes:
  mysql_data:
  redis_data:
  node_modules:
```

### Production Environment

For production, the application is deployed using Docker Swarm for better performance and scalability:

```yaml
version: "3.8"

services:
  node:
    image: newsblog:dev
    build:
      context: .
      dockerfile: Dockerfile.dev
    user: node
    working_dir: /usr/src/app
    volumes:
      - .:/usr/src/app
      - node_modules:/usr/src/app/node_modules
    environment:
      - NODE_ENV=production
      - CHOKIDAR_USEPOLLING=true
    command: npm start
    deploy:
      mode: replicated
      replicas: 8
      restart_policy:
        condition: on-failure
    logging:
      driver: "json-file"
      options:
        max-size: "10m"
        max-file: "3"
    networks:
      - private
    depends_on:
      - mysql
      - redis

  mysql:
    image: mysql:8.4
    environment:
      MYSQL_ROOT_PASSWORD: $password
      MYSQL_DATABASE: news_blog
      MYSQL_USER: news_blog
      MYSQL_PASSWORD: $password
    volumes:
      - mysql_data:/var/lib/mysql
    deploy:
      mode: replicated
      replicas: 1
      placement:
        constraints:
          - node.role == manager
    networks:
      - private

  redis:
    image: redis:latest
    volumes:
      - redis_data:/data
    deploy:
      mode: replicated
      replicas: 1
    networks:
      - private

  phpmyadmin:
    image: phpmyadmin:latest
    environment:
      UPLOAD_LIMIT: 64M
      PMA_HOST: mysql
      PMA_PORT: 3306
    ports:
      - published: 8101
        target: 80
        mode: host
    networks:
      - public
      - private
    deploy:
      mode: replicated
      replicas: 1
    depends_on:
      - mysql

  nginx:
    image: nginx:latest
    volumes:
      - ../frontend/dist:/usr/share/nginx/html/news:ro
      - ../admin/dist:/usr/share/nginx/html/admin:ro
      - ./nginx.conf:/etc/nginx/conf.d/default.conf:ro
      - ./ssl/main:/etc/nginx/ssl/news:ro
      - ./ssl/admin:/etc/nginx/ssl/admin:ro
      - ./ssl/api:/etc/nginx/ssl/api:ro
    ports:
      - published: 80
        target: 80
        mode: host
      - published: 443
        target: 443
        mode: host
    networks:
      - public
      - private
    deploy:
      mode: replicated
      replicas: 1
      restart_policy:
        condition: on-failure
    depends_on:
      - node

networks:
  public:
    driver: overlay
    attachable: true
  private:
    driver: overlay
    attachable: true
    internal: false

volumes:
  mysql_data:
  redis_data:
  node_modules:
```

---

## Webserver

### Nginx Configuration

The webserver is configured using Nginx to serve the main site, admin panel, and API. Below is the Nginx configuration:

```nginx
# Frontend nginx configuration

# Redirect HTTP to HTTPS
server {
    listen 80;
    server_name news.vedina.ir admin.news.vedina.ir api.news.vedina.ir;
    return 301 https://$server_name$request_uri;
}

# Main website
server {
    listen 443 ssl;
    server_name news.vedina.ir;

    # SSL configuration
    ssl_certificate /etc/nginx/ssl/news/fullchain.pem;
    ssl_certificate_key /etc/nginx/ssl/news/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;
    ssl_prefer_server_ciphers off;
    ssl_session_timeout 1d;
    ssl_session_cache shared:SSL:50m;
    ssl_session_tickets off;

    root /usr/share/nginx/html/news;
    index index.html;

    # Security headers
    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-XSS-Protection "1; mode=block";
    add_header X-Content-Type-Options "nosniff";
    add_header Referrer-Policy "strict-origin-when-cross-origin";
    add_header Content-Security-Policy "default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline'; img-src 'self' data: https:; font-src 'self' data:; connect-src 'self' https://api.news.vedina.ir";
    add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;

    # Gzip compression
    gzip_static on;
    gzip_vary on;
    gzip_proxied any;
    gzip_types text/plain text/css text/javascript application/javascript application/x-javascript text/xml application/xml application/xml+rss application/json image/svg+xml;

    location / {
        try_files $uri $uri/ /index.html;
    }

    # Cache control for static files
    location ~* \.(jpg|jpeg|webp|png|gif|ico|css|js)$ {
        expires 1y;
        add_header Cache-Control "public, no-transform";
    }
}

# Admin panel
server {
    listen 443 ssl;
    server_name admin.news.vedina.ir;

    # SSL configuration
    ssl_certificate /etc/nginx/ssl/admin/fullchain.pem;
    ssl_certificate_key /etc/nginx/ssl/admin/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;
    ssl_prefer_server_ciphers off;
    ssl_session_timeout 1d;
    ssl_session_cache shared:SSL:50m;
    ssl_session_tickets off;

    root /usr/share/nginx/html/admin;
    index index.html;

    # Security headers
    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-XSS-Protection "1; mode=block";
    add_header X-Content-Type-Options "nosniff";
    add_header Referrer-Policy "strict-origin-when-cross-origin";
    add_header Content-Security-Policy "default-src 'self'; script-src 'self' 'unsafe-inline' 'unsafe-eval'; style-src 'self' 'unsafe-inline'; img-src 'self' data: https:; font-src 'self' data:; connect-src 'self' https://api.news.vedina.ir";
    add_header Strict-Transport-Security "max-age=31536000; includeSubDomains" always;

    # Gzip compression
    gzip_static on;
    gzip_vary on;
    gzip_proxied any;
    gzip_types text/plain text/css text/javascript application/javascript application/x-javascript text/xml application/xml application/xml+rss application/json image/svg+xml;

    location / {
        try_files $uri $uri/ /index.html;
    }

    # Cache control for static files
    location ~* \.(jpg|jpeg|webp|png|gif|ico|css|js)$ {
        expires 1y;
        add_header Cache-Control "public, no-transform";
    }
}

# API proxy
server {
    listen 443 ssl;
    server_name api.news.vedina.ir;

    # SSL configuration
    ssl_certificate /etc/nginx/ssl/api/fullchain.pem;
    ssl_certificate_key /etc/nginx/ssl/api/privkey.pem;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384;
    ssl_prefer_server_ciphers off;
    ssl_session_timeout 1d;
    ssl_session_cache shared:SSL:50m;
    ssl_session_tickets off;

    #WEBSOCKET-SUPPORT START
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";
    #WEBSOCKET-SUPPORT END

    #PROXY-CONF-START
    location ^~ / {
      proxy_pass http://node:3000;
      proxy_set_header Host $http_host;
      proxy_set_header X-Real-IP $remote_addr;
      proxy_set_header X-Real-Port $remote_port;
      proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
      proxy_set_header REMOTE-HOST $remote_addr;
      proxy_connect_timeout 60s;
      proxy_send_timeout 600s;
      proxy_read_timeout 600s;
      proxy_http_version 1.1;
      proxy_set_header Upgrade $http_upgrade;
      proxy_set_header Connection "upgrade";
    }
}

# DOS protection settings
# limit_req_zone $binary_remote_addr zone=one:10m rate=1r/s;
# limit_conn_zone $binary_remote_addr zone=addr:10m;
```

### Security and Performance

- **SSL/TLS:** Enforced for all HTTPS communications.
- **Security Headers:** Added headers to enhance security (e.g., Content Security Policy, X-Frame-Options).
- **Gzip Compression:** Enabled to reduce the size of the response payload.
- **Caching:** Configured to cache static assets for better performance.
- **Reverse Proxy:** Nginx acts as a reverse proxy to route API requests to the backend without exposing the API server directly.

---

## Conclusion

Vedina News is a robust and scalable platform built with a focus on performance, security, and maintainability. The architecture leverages modern technologies and best practices to ensure a seamless experience for users and administrators alike.

---

## Future Enhancements

- **Microservices Architecture:** Consider breaking down the monolithic backend into microservices for better scalability and maintainability.
- **AI-Driven Content Analysis:** Implement AI-driven content analysis for better recommendations and user engagement.
- **Globalization:** Add support for multiple languages and regions.
- **Advanced Analytics:** Integrate advanced analytics tools for deeper insights into user behavior.

---

**Note:** The source code and proprietary technologies mentioned in this documentation are owned by Vedina Co. and are intended for commercial and business usage only.
