# Fullstack Java Travel Blog

Fullstack Java Travel Blog is a complete travel website project that includes:
- a static front-end with HTML/CSS/JavaScript pages for blogs, categories, detail views, admin, and search;
- a Spring Boot back-end handling APIs, user authentication, content management, image uploads, and comments.

## Overview

This project simulates a travel blog system, allowing users to:
- create and manage travel posts;
- upload images and attach them to posts;
- comment on posts;
- browse public blogs, search by keyword, and view the latest posts.

## Project Architecture

- `client/` - static front-end interface containing HTML, CSS, SCSS, JS, and media assets.
- `server/` - Java Spring Boot back-end connected to MongoDB and exposing REST APIs.

## Technologies Used

- Front-end: HTML5, CSS3, SCSS, JavaScript, Bootstrap
- Back-end: Java, Spring Boot, Spring MVC, Spring Data MongoDB, Spring WebSocket
- Database: MongoDB
- Image storage: Cloudinary
- Authentication: JWT and password hashing
- API documentation: SpringDoc OpenAPI
- Build system: Maven (Maven Wrapper included)

## Highlights

- Clear fullstack architecture with separate front-end and back-end.
- RESTful APIs for blogs, users, images, and comments.
- Image upload support via Cloudinary.
- WebSocket support for realtime features.
- MapStruct and Lombok reduce boilerplate in the service layer.

## Setup and Run

### Backend

1. Open the `server` directory:
    ```bash
    cd server
    ```

2. Run the application using the Maven Wrapper:
    - On Windows:
      ```powershell
      ./mvnw.cmd spring-boot:run
      ```
    - On macOS / Linux:
      ```bash
      ./mvnw spring-boot:run
      ```

3. Alternatively, build the package and run the JAR file:
    ```bash
    ./mvnw package -DskipTests
    java -jar target/blogdulich-0.0.1-SNAPSHOT.jar
    ```

### Frontend

- Open `client/index.html` directly in a browser.
- Or serve the `client/` folder with a static server if you need multiple pages at once.

## Recommended Environment Variables

The backend requires connection and third-party service configuration. Create a `.env` file in `server/` with values like:

```text
MONGODB_URI=<your_mongodb_connection_string>
CLOUD_NAME=<your_cloudinary_cloud_name>
CLOUD_API_KEY=<your_cloudinary_api_key>
CLOUD_API_SECRET=<your_cloudinary_api_secret>
```

> If the project also uses JWT or additional security settings, add the relevant environment variables as needed.

## Main Endpoints

- `POST /api/user` - create a new user
- `POST /api/user/signin` - sign in
- `GET /api/user/me` - get current user info
- `GET /api/user/all` - get all users
- `POST /api/blog` - create a new blog post
- `PUT /api/blog/{id}` - update a blog post
- `DELETE /api/blog/{id}` - delete a blog post
- `GET /api/blog/all` - get all blog posts
- `GET /api/blog/public` - get public blog posts
- `GET /api/blog/newest` - get newest posts
- `GET /api/blog/home` - get homepage content
- `POST /api/image` - upload an image
- `DELETE /api/image/{id}` - delete an image
- `POST /api/comment` - add a comment
- `GET /api/comment/{blogId}` - get comments for a post

## Main Directory Structure

- `client/` - front-end for landing pages, blog pages, contact, admin, HTML/CSS/JS
- `server/src/main/java` - Spring Boot source code
- `server/src/main/resources` - Spring Boot app configuration and resources
- `server/src/test/java` - basic unit tests

## Expansion and Development

- Connect the front-end to the API using AJAX/Fetch or a SPA framework.
- Add an admin/user role-based authorization system.
- Complete WebSocket features for chat or realtime notifications.
- Deploy to cloud using Docker or a PaaS platform.

## Notes

- The current front-end is static and can be upgraded to a SPA.
- The backend uses MongoDB, so it needs connection to a local or remote database.
- This structure is suitable for evolving into a multi-user travel/blog platform.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
