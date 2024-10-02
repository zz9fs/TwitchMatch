# TwitchMatch

Sure, here's an expanded README file for your "Twitch Match: A Personalized Twitch Resources Recommendation Engine" project:

---

# Twitch Match: A Personalized Twitch Resources Recommendation Engine

Twitch Match is a full-stack application that provides users with personalized recommendations for Twitch resources, including streams, videos, and clips. This project aims to enhance the Twitch experience by allowing users to search for and receive suggestions based on their preferences and viewing history. The application is built using Spring Boot for the backend and React with Ant Design for the frontend.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Architecture](#architecture)
- [API Documentation](#api-documentation)
- [Caching and Performance](#caching-and-performance)
- [Authentication](#authentication)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Search for Twitch Resources**: Search for streams, videos, and clips in real-time.
- **Personalized Recommendations**: Receive tailored recommendations based on viewing patterns and preferences.
- **User Authentication**: Register, log in, and log out securely with Spring Security.
- **Real-Time Data**: Retrieve Twitch resources in real-time using the OpenFeign HTTP client.
- **CRUD Operations**: Manage user profiles, preferences, and favorites using CRUD functionalities.
- **Caching for Performance**: Improve performance using Spring Boot Caching with Caffeine.
- **Containerized Deployment**: Deploy seamlessly using Docker and AWS App Runner.

## Tech Stack

**Backend:**
- Java with Spring Boot
- Spring Data JDBC for database operations
- Spring Security for authentication
- OpenFeign for API communication
- Caffeine for caching

**Frontend:**
- React
- Ant Design for UI components

**Database:**
- MySQL hosted on AWS RDS

**Deployment:**
- Docker for containerization
- AWS App Runner for deployment

## Installation

To run this project locally, you need to have Docker installed along with Java 17+ and Node.js. Follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/twitch-match.git
   cd twitch-match
   ```

2. **Backend Setup**:
   - Navigate to the backend directory:
     ```bash
     cd backend
     ```
   - Create an application.properties file in `src/main/resources`:
     ```properties
     spring.datasource.url=jdbc:mysql://<AWS_RDS_ENDPOINT>:3306/twitchmatch
     spring.datasource.username=<db-username>
     spring.datasource.password=<db-password>
     twitch.api.clientId=<your-twitch-client-id>
     twitch.api.clientSecret=<your-twitch-client-secret>
     ```
   - Build the backend using Maven:
     ```bash
     ./mvnw clean install
     ```
   - Start the backend server:
     ```bash
     ./mvnw spring-boot:run
     ```

3. **Frontend Setup**:
   - Navigate to the frontend directory:
     ```bash
     cd ../frontend
     ```
   - Install dependencies:
     ```bash
     npm install
     ```
   - Start the frontend development server:
     ```bash
     npm start
     ```

4. **Running with Docker**:
   - Build and run the Docker containers:
     ```bash
     docker-compose up
     ```

## Usage

1. Visit `http://localhost:3000` in your browser to access the application.
2. Create an account or log in to start using Twitch Match.
3. Use the search bar to find Twitch resources (streams, videos, clips).
4. Save favorites and view personalized recommendations.

## Architecture

Twitch Match is structured with a modular architecture for easy scalability and maintenance:

- **Frontend**: The user interface is built with React and Ant Design, providing a modern and intuitive experience.
- **Backend**: The Spring Boot backend handles API requests, processes user data, and manages interactions with the Twitch API.
- **Database**: User data, preferences, and resource metadata are stored in a MySQL database hosted on AWS RDS.

### API Documentation

The backend exposes a set of RESTful APIs that handle all operations of the application. These APIs include:

1. **User Authentication API**:
   - `POST /api/auth/register`: Register a new user.
   - `POST /api/auth/login`: Log in with an existing account.
   - `POST /api/auth/logout`: Log out from the current session.

2. **Twitch Resource API**:
   - `GET /api/resources/search`: Search for streams, videos, or clips.
   - `GET /api/resources/recommend`: Get personalized recommendations for the user.

3. **User Preferences API**:
   - `POST /api/user/favorites`: Add a resource to favorites.
   - `GET /api/user/favorites`: Retrieve all favorited resources.

### Caching and Performance

To optimize performance, Twitch Match uses **Spring Boot Caching** with **Caffeine** for the following:

- Caching popular Twitch resource searches.
- Reducing redundant API requests to Twitch, which minimizes latency.

### Authentication

The application employs **Spring Security** for user authentication. Users can register, log in, and log out using secure authentication methods. Passwords are hashed and stored securely to ensure data protection.

### Deployment

The application is containerized using Docker to facilitate easy deployment. It is hosted on **AWS App Runner** for scalability and reliability. The database is managed via **AWS RDS**, ensuring persistence and backup.

To deploy your own version, follow these steps:

1. Build the Docker image:
   ```bash
   docker build -t twitch-match .
   ```
2. Push the Docker image to your container registry.
3. Use AWS App Runner or an equivalent service to deploy the container.

## Contributing

Contributions are welcome! If you'd like to contribute to Twitch Match, follow these steps:

1. Fork the repository.
2. Create a new branch:
   ```bash
   git checkout -b feature-name
   ```
3. Make your changes and commit:
   ```bash
   git commit -m "Add feature name"
   ```
4. Push the branch:
   ```bash
   git push origin feature-name
   ```
5. Open a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to further customize this README to fit your project's needs. Adding screenshots, usage examples, or links to related resources can make it even more engaging.
